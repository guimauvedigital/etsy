# ShopProcessingProfilesApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createShopReadinessStateDefinition**](ShopProcessingProfilesApi.md#createShopReadinessStateDefinition) | **POST** /v3/application/shops/{shop_id}/readiness-state-definitions |  |
| [**deleteShopReadinessStateDefinition**](ShopProcessingProfilesApi.md#deleteShopReadinessStateDefinition) | **DELETE** /v3/application/shops/{shop_id}/readiness-state-definitions/{readiness_state_definition_id} |  |
| [**getShopReadinessStateDefinition**](ShopProcessingProfilesApi.md#getShopReadinessStateDefinition) | **GET** /v3/application/shops/{shop_id}/readiness-state-definitions/{readiness_state_definition_id} |  |
| [**getShopReadinessStateDefinitions**](ShopProcessingProfilesApi.md#getShopReadinessStateDefinitions) | **GET** /v3/application/shops/{shop_id}/readiness-state-definitions |  |
| [**updateShopReadinessStateDefinition**](ShopProcessingProfilesApi.md#updateShopReadinessStateDefinition) | **PUT** /v3/application/shops/{shop_id}/readiness-state-definitions/{readiness_state_definition_id} |  |


<a id="createShopReadinessStateDefinition"></a>
# **createShopReadinessStateDefinition**
> ShopProcessingProfile createShopReadinessStateDefinition(shopId, readinessState, minProcessingTime, maxProcessingTime, processingTimeUnit)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Creates a new ReadinessStateDefinition. If an existing definition matches the input values, this endpoint will throw a Conflict error, please refer to the Content-Location header to obtain the get endpoint url for the values of the existing definition. Does not affect the product offering-readiness states definition relationship.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopProcessingProfilesApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val readinessState : kotlin.String = readinessState_example // kotlin.String | The readiness state of a product: \\\\\\\"1\\\\\\\" means \\\\\\\"ready_to_ship\\\\\\\", and \\\\\\\"2\\\\\\\" means \\\\\\\"made_to_order\\\\\\\"
val minProcessingTime : kotlin.Int = 56 // kotlin.Int | The minimum number of days or weeks for processing a specific product.
val maxProcessingTime : kotlin.Int = 56 // kotlin.Int | The maximum number of days or weeks for processing a specific product.
val processingTimeUnit : kotlin.String = processingTimeUnit_example // kotlin.String | The unit used to represent how long a processing time is. A week is equivalent to how many days the seller works per week as stated in their processing schedule. If none is provided, the unit is set to \\\\\\\"days\\\\\\\".
try {
    val result : ShopProcessingProfile = apiInstance.createShopReadinessStateDefinition(shopId, readinessState, minProcessingTime, maxProcessingTime, processingTimeUnit)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopProcessingProfilesApi#createShopReadinessStateDefinition")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopProcessingProfilesApi#createShopReadinessStateDefinition")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **readinessState** | **kotlin.String**| The readiness state of a product: \\\\\\\&quot;1\\\\\\\&quot; means \\\\\\\&quot;ready_to_ship\\\\\\\&quot;, and \\\\\\\&quot;2\\\\\\\&quot; means \\\\\\\&quot;made_to_order\\\\\\\&quot; | [enum: ready_to_ship, made_to_order] |
| **minProcessingTime** | **kotlin.Int**| The minimum number of days or weeks for processing a specific product. | |
| **maxProcessingTime** | **kotlin.Int**| The maximum number of days or weeks for processing a specific product. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **processingTimeUnit** | **kotlin.String**| The unit used to represent how long a processing time is. A week is equivalent to how many days the seller works per week as stated in their processing schedule. If none is provided, the unit is set to \\\\\\\&quot;days\\\\\\\&quot;. | [optional] [default to days] [enum: days, weeks] |

### Return type

[**ShopProcessingProfile**](ShopProcessingProfile.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="deleteShopReadinessStateDefinition"></a>
# **deleteShopReadinessStateDefinition**
> deleteShopReadinessStateDefinition(shopId, readinessStateDefinitionId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Deletes a ReadinessStateDefinition by given readiness state definition ID. If there any active offerings linked to the definition, this endpoint will throw a Bad Request error. If you want to delete a ReadinessStateDefinition that is linked to active offerings, you must link the offerings to a different readiness state definition.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopProcessingProfilesApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val readinessStateDefinitionId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is `physical`.
try {
    apiInstance.deleteShopReadinessStateDefinition(shopId, readinessStateDefinitionId)
} catch (e: ClientException) {
    println("4xx response calling ShopProcessingProfilesApi#deleteShopReadinessStateDefinition")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopProcessingProfilesApi#deleteShopReadinessStateDefinition")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **readinessStateDefinitionId** | **kotlin.Long**| The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |

### Return type

null (empty response body)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopReadinessStateDefinition"></a>
# **getShopReadinessStateDefinition**
> ShopProcessingProfile getShopReadinessStateDefinition(shopId, readinessStateDefinitionId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a ProcessingProfile referenced by readiness state definition ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopProcessingProfilesApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val readinessStateDefinitionId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is `physical`.
try {
    val result : ShopProcessingProfile = apiInstance.getShopReadinessStateDefinition(shopId, readinessStateDefinitionId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopProcessingProfilesApi#getShopReadinessStateDefinition")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopProcessingProfilesApi#getShopReadinessStateDefinition")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **readinessStateDefinitionId** | **kotlin.Long**| The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |

### Return type

[**ShopProcessingProfile**](ShopProcessingProfile.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopReadinessStateDefinitions"></a>
# **getShopReadinessStateDefinitions**
> ShopProcessingProfiles getShopReadinessStateDefinitions(shopId, limit, offset)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a list of ProcessingProfiles available in the specific Etsy shop identified by its shop ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopProcessingProfilesApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
try {
    val result : ShopProcessingProfiles = apiInstance.getShopReadinessStateDefinitions(shopId, limit, offset)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopProcessingProfilesApi#getShopReadinessStateDefinitions")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopProcessingProfilesApi#getShopReadinessStateDefinitions")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |

### Return type

[**ShopProcessingProfiles**](ShopProcessingProfiles.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateShopReadinessStateDefinition"></a>
# **updateShopReadinessStateDefinition**
> ShopProcessingProfile updateShopReadinessStateDefinition(shopId, readinessStateDefinitionId, readinessState, minProcessingTime, maxProcessingTime, processingTimeUnit)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates an existing ReadinessStateDefinition. If an existing definition matches the input values, this endpoint will throw a Conflict error, please refer to the Content-Location header to obtain the get endpoint url for the values of the existing definition. Does not affect the product offering-readiness states definition relationship.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopProcessingProfilesApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val readinessStateDefinitionId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is `physical`.
val readinessState : kotlin.String = readinessState_example // kotlin.String | The readiness state of a product: \\\\\\\"1\\\\\\\" means \\\\\\\"ready_to_ship\\\\\\\", and \\\\\\\"2\\\\\\\" means \\\\\\\"made_to_order\\\\\\\"
val minProcessingTime : kotlin.Int = 56 // kotlin.Int | The minimum number of days or weeks for processing a specific product.
val maxProcessingTime : kotlin.Int = 56 // kotlin.Int | The maximum number of days or weeks for processing a specific product.
val processingTimeUnit : kotlin.String = processingTimeUnit_example // kotlin.String | The unit used to represent how long a processing time is. A week is equivalent to how many days the seller works per week as stated in their processing schedule. If none is provided, the unit is set to \\\\\\\"days\\\\\\\".
try {
    val result : ShopProcessingProfile = apiInstance.updateShopReadinessStateDefinition(shopId, readinessStateDefinitionId, readinessState, minProcessingTime, maxProcessingTime, processingTimeUnit)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopProcessingProfilesApi#updateShopReadinessStateDefinition")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopProcessingProfilesApi#updateShopReadinessStateDefinition")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **readinessStateDefinitionId** | **kotlin.Long**| The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |
| **readinessState** | **kotlin.String**| The readiness state of a product: \\\\\\\&quot;1\\\\\\\&quot; means \\\\\\\&quot;ready_to_ship\\\\\\\&quot;, and \\\\\\\&quot;2\\\\\\\&quot; means \\\\\\\&quot;made_to_order\\\\\\\&quot; | [optional] [enum: ready_to_ship, made_to_order] |
| **minProcessingTime** | **kotlin.Int**| The minimum number of days or weeks for processing a specific product. | [optional] |
| **maxProcessingTime** | **kotlin.Int**| The maximum number of days or weeks for processing a specific product. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **processingTimeUnit** | **kotlin.String**| The unit used to represent how long a processing time is. A week is equivalent to how many days the seller works per week as stated in their processing schedule. If none is provided, the unit is set to \\\\\\\&quot;days\\\\\\\&quot;. | [optional] [default to days] [enum: days, weeks] |

### Return type

[**ShopProcessingProfile**](ShopProcessingProfile.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

