# ShopProductionPartnerApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getShopProductionPartners**](ShopProductionPartnerApi.md#getShopProductionPartners) | **GET** /v3/application/shops/{shop_id}/production-partners |  |


<a id="getShopProductionPartners"></a>
# **getShopProductionPartners**
> ShopProductionPartners getShopProductionPartners(shopId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a list of production partners available in the specific Etsy shop identified by its shop ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopProductionPartnerApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
try {
    val result : ShopProductionPartners = apiInstance.getShopProductionPartners(shopId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopProductionPartnerApi#getShopProductionPartners")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopProductionPartnerApi#getShopProductionPartners")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |

### Return type

[**ShopProductionPartners**](ShopProductionPartners.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

