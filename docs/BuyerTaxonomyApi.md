# BuyerTaxonomyApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBuyerTaxonomyNodes**](BuyerTaxonomyApi.md#getBuyerTaxonomyNodes) | **GET** /v3/application/buyer-taxonomy/nodes |  |
| [**getPropertiesByBuyerTaxonomyId**](BuyerTaxonomyApi.md#getPropertiesByBuyerTaxonomyId) | **GET** /v3/application/buyer-taxonomy/nodes/{taxonomy_id}/properties |  |


<a id="getBuyerTaxonomyNodes"></a>
# **getBuyerTaxonomyNodes**
> BuyerTaxonomyNodes getBuyerTaxonomyNodes()



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves the full hierarchy tree of buyer taxonomy nodes.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = BuyerTaxonomyApi()
try {
    val result : BuyerTaxonomyNodes = apiInstance.getBuyerTaxonomyNodes()
    println(result)
} catch (e: ClientException) {
    println("4xx response calling BuyerTaxonomyApi#getBuyerTaxonomyNodes")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling BuyerTaxonomyApi#getBuyerTaxonomyNodes")
    e.printStackTrace()
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**BuyerTaxonomyNodes**](BuyerTaxonomyNodes.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getPropertiesByBuyerTaxonomyId"></a>
# **getPropertiesByBuyerTaxonomyId**
> BuyerTaxonomyNodeProperties getPropertiesByBuyerTaxonomyId(taxonomyId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a list of product properties, with applicable scales and values, supported for a specific buyer taxonomy ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = BuyerTaxonomyApi()
val taxonomyId : kotlin.Long = 789 // kotlin.Long | The unique numeric ID of an Etsy taxonomy node, which is a metadata category for listings organized into the seller taxonomy hierarchy tree. For example, the \"shoes\" taxonomy node (ID: 1429, level: 1) is higher in the hierarchy than \"girls' shoes\" (ID: 1440, level: 2). The taxonomy nodes assigned to a listing support access to specific standardized product scales and properties. For example, listings assigned the taxonomy nodes \"shoes\" or \"girls' shoes\" support access to the \"EU\" shoe size scale with its associated property names and IDs for EU shoe sizes, such as property `value_id`:\"1394\", and `name`:\"38\".
try {
    val result : BuyerTaxonomyNodeProperties = apiInstance.getPropertiesByBuyerTaxonomyId(taxonomyId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling BuyerTaxonomyApi#getPropertiesByBuyerTaxonomyId")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling BuyerTaxonomyApi#getPropertiesByBuyerTaxonomyId")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **taxonomyId** | **kotlin.Long**| The unique numeric ID of an Etsy taxonomy node, which is a metadata category for listings organized into the seller taxonomy hierarchy tree. For example, the \&quot;shoes\&quot; taxonomy node (ID: 1429, level: 1) is higher in the hierarchy than \&quot;girls&#39; shoes\&quot; (ID: 1440, level: 2). The taxonomy nodes assigned to a listing support access to specific standardized product scales and properties. For example, listings assigned the taxonomy nodes \&quot;shoes\&quot; or \&quot;girls&#39; shoes\&quot; support access to the \&quot;EU\&quot; shoe size scale with its associated property names and IDs for EU shoe sizes, such as property &#x60;value_id&#x60;:\&quot;1394\&quot;, and &#x60;name&#x60;:\&quot;38\&quot;. | |

### Return type

[**BuyerTaxonomyNodeProperties**](BuyerTaxonomyNodeProperties.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

