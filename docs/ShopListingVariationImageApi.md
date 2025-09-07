# ShopListingVariationImageApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getListingVariationImages**](ShopListingVariationImageApi.md#getListingVariationImages) | **GET** /v3/application/shops/{shop_id}/listings/{listing_id}/variation-images |  |
| [**updateVariationImages**](ShopListingVariationImageApi.md#updateVariationImages) | **POST** /v3/application/shops/{shop_id}/listings/{listing_id}/variation-images |  |


<a id="getListingVariationImages"></a>
# **getListingVariationImages**
> ListingVariationImages getListingVariationImages(shopId, listingId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Gets all variation images on a listing.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingVariationImageApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
try {
    val result : ListingVariationImages = apiInstance.getListingVariationImages(shopId, listingId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingVariationImageApi#getListingVariationImages")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingVariationImageApi#getListingVariationImages")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |

### Return type

[**ListingVariationImages**](ListingVariationImages.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateVariationImages"></a>
# **updateVariationImages**
> ListingVariationImages updateVariationImages(shopId, listingId, updateVariationImagesRequest)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Creates variation images on a listing. &#x60;variation_images&#x60; is an array with inputs for the &#x60;property_id&#x60;, &#x60;value_id&#x60;, and &#x60;image_id&#x60; fields. &#x60;image_ids&#x60; are associated with a &#x60;ListingImage&#x60; on the listing associated with the provided &#x60;listing_id&#x60;. &#x60;property_id&#x60; and &#x60;value_id&#x60; pairs are associated with a &#x60;ListingProduct&#x60; on the listing associated with the provided &#x60;listing_id&#x60;. &#x60;variation_images&#x60; should not contain any duplicates. &#x60;variation_images&#x60; does not contain more than one &#x60;property_id&#x60; as variation images can only be associated on one property. The update overwrites all existing variation images on a listing, so if your request is successful, the variation images on the listing will be exactly those you specify. 

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingVariationImageApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val updateVariationImagesRequest : UpdateVariationImagesRequest =  // UpdateVariationImagesRequest | 
try {
    val result : ListingVariationImages = apiInstance.updateVariationImages(shopId, listingId, updateVariationImagesRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingVariationImageApi#updateVariationImages")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingVariationImageApi#updateVariationImages")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateVariationImagesRequest** | [**UpdateVariationImagesRequest**](UpdateVariationImagesRequest.md)|  | [optional] |

### Return type

[**ListingVariationImages**](ListingVariationImages.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

