# ShopListingProductApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getListingProduct**](ShopListingProductApi.md#getListingProduct) | **GET** /v3/application/listings/{listing_id}/inventory/products/{product_id} |  |


<a id="getListingProduct"></a>
# **getListingProduct**
> ListingInventoryProduct getListingProduct(listingId, productId, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 endpoint to retrieve a ListingProduct by ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingProductApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The listing to return a ListingProduct for.
val productId : kotlin.Long = 789 // kotlin.Long | The numeric ID for a specific [product](/documentation/reference#tag/ShopListing-Product) purchased from a listing.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ListingInventoryProduct = apiInstance.getListingProduct(listingId, productId, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingProductApi#getListingProduct")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingProductApi#getListingProduct")
    e.printStackTrace()
}
```

### Parameters
| **listingId** | **kotlin.Long**| The listing to return a ListingProduct for. | |
| **productId** | **kotlin.Long**| The numeric ID for a specific [product](/documentation/reference#tag/ShopListing-Product) purchased from a listing. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ListingInventoryProduct**](ListingInventoryProduct.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

