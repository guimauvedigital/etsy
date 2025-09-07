# Generate the base project

```kotlin
import com.fasterxml.jackson.databind.ObjectMapper
import com.fasterxml.jackson.databind.node.ObjectNode
import com.fasterxml.jackson.module.kotlin.jacksonObjectMapper
import org.openapitools.generator.gradle.plugin.tasks.GenerateTask
import java.net.URL

plugins {
    alias(libs.plugins.openapi)
}

val openApiSpec = layout.buildDirectory.file("openapi/etsy.json")
val generatedSrcDir = layout.projectDirectory.dir("./")

tasks.register("downloadEtsySpec") {
    group = "openapi"
    outputs.file(openApiSpec)
    doLast {
        val url = URL("https://www.etsy.com/openapi/generated/oas/3.0.0.json")
        val targetFile = openApiSpec.get().asFile
        targetFile.parentFile.mkdirs()
        url.openStream().use { input ->
            targetFile.outputStream().use { output ->
                input.copyTo(output)
            }
        }
        println("Downloaded Etsy OpenAPI spec to: ${targetFile.absolutePath}")
    }
}

tasks.register("sanitizeEtsySpec") {
    group = "openapi"
    dependsOn("downloadEtsySpec")
    outputs.file(openApiSpec)

    doLast {
        val mapper: ObjectMapper = jacksonObjectMapper()
        val file = openApiSpec.get().asFile
        val root = mapper.readTree(file)

        root.path("paths").fields().forEachRemaining { (_, pathItem) ->
            pathItem.fields().forEachRemaining { (_, op) ->
                val params = op.path("parameters")
                if (params.isArray) {
                    params.forEach { param ->
                        val schema = param.path("schema") as? ObjectNode
                        if (schema != null && schema.path("type").asText() == "array") {
                            val defaultNode = schema.get("default")
                            if (defaultNode != null && !defaultNode.isArray) {
                                (schema as ObjectNode).remove("default")
                            }
                        }
                    }
                }
            }
        }

        mapper.writerWithDefaultPrettyPrinter().writeValue(file, root)
        println("Sanitized Etsy spec written to: ${file.absolutePath}")
    }
}

tasks.register<GenerateTask>("generateEtsyClient") {
    dependsOn("sanitizeEtsySpec")
    group = "openapi"
    description = "Generates Etsy API client using OpenAPI Generator"

    generatorName.set("kotlin")
    inputSpec.set(openApiSpec.get().asFile.absolutePath)
    outputDir.set(generatedSrcDir.asFile.absolutePath)
    cleanupOutput.set(true)
    packageName.set("com.etsy")
    groupId.set("digital.guimauve.etsy")
    version.set("1.0.0")

    additionalProperties.set(
        mapOf(
            "library" to "multiplatform",
            "dateLibrary" to "kotlinx-datetime"
        )
    )
}
```
