# ShopListingImageApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteListingImage**](ShopListingImageApi.md#deleteListingImage) | **DELETE** /v3/application/shops/{shop_id}/listings/{listing_id}/images/{listing_image_id} |  |
| [**getListingImage**](ShopListingImageApi.md#getListingImage) | **GET** /v3/application/listings/{listing_id}/images/{listing_image_id} |  |
| [**getListingImages**](ShopListingImageApi.md#getListingImages) | **GET** /v3/application/listings/{listing_id}/images |  |
| [**uploadListingImage**](ShopListingImageApi.md#uploadListingImage) | **POST** /v3/application/shops/{shop_id}/listings/{listing_id}/images |  |


<a id="deleteListingImage"></a>
# **deleteListingImage**
> deleteListingImage(shopId, listingId, listingImageId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 endpoint to delete a listing image. A copy of the file remains on our servers, and so a deleted image may be re-associated with the listing without re-uploading the original image; see uploadListingImage.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingImageApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val listingImageId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the primary [listing image](/documentation/reference#tag/ShopListing-Image) for this transaction.
try {
    apiInstance.deleteListingImage(shopId, listingId, listingImageId)
} catch (e: ClientException) {
    println("4xx response calling ShopListingImageApi#deleteListingImage")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingImageApi#deleteListingImage")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingImageId** | **kotlin.Long**| The numeric ID of the primary [listing image](/documentation/reference#tag/ShopListing-Image) for this transaction. | |

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

<a id="getListingImage"></a>
# **getListingImage**
> ListingImage getListingImage(listingId, listingImageId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves the references and metadata for a listing image with a specific image ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingImageApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val listingImageId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the primary [listing image](/documentation/reference#tag/ShopListing-Image) for this transaction.
try {
    val result : ListingImage = apiInstance.getListingImage(listingId, listingImageId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingImageApi#getListingImage")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingImageApi#getListingImage")
    e.printStackTrace()
}
```

### Parameters
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingImageId** | **kotlin.Long**| The numeric ID of the primary [listing image](/documentation/reference#tag/ShopListing-Image) for this transaction. | |

### Return type

[**ListingImage**](ListingImage.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingImages"></a>
# **getListingImages**
> ListingImages getListingImages(listingId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves all listing image resources for a listing with a specific listing ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingImageApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
try {
    val result : ListingImages = apiInstance.getListingImages(listingId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingImageApi#getListingImages")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingImageApi#getListingImages")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |

### Return type

[**ListingImages**](ListingImages.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="uploadListingImage"></a>
# **uploadListingImage**
> ListingImage uploadListingImage(shopId, listingId, image, listingImageId, rank, overwrite, isWatermarked, altText)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Uploads or assigns an image to a listing identified by a shop ID with a listing ID. To upload a new image, set the image file as the value for the &#x60;image&#x60; parameter. You can assign a previously deleted image to a listing using the deleted image&#39;s image ID in the &#x60;listing_image_id&#x60; parameter. When a request contains both &#x60;image&#x60; and &#x60;listing_image_id&#x60; parameter values, the endpoint uploads the image in the &#x60;image&#x60; parameter only. Note: When uploading a new image, data such as colors and size may return as null values due to asynchronous processing of the image. Use getListingImage endpoint to fetch these values.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingImageApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val image : io.ktor.client.request.forms.FormPart<io.ktor.client.request.forms.InputProvider> = BINARY_DATA_HERE // io.ktor.client.request.forms.FormPart<io.ktor.client.request.forms.InputProvider> | The file name string of a file to upload
val listingImageId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the primary [listing image](/documentation/reference#tag/ShopListing-Image) for this transaction.
val rank : kotlin.Int = 56 // kotlin.Int | The positive non-zero numeric position in the images displayed in a listing, with rank 1 images appearing in the left-most position in a listing.
val overwrite : kotlin.Boolean = true // kotlin.Boolean | When true, this request replaces the existing image at a given rank.
val isWatermarked : kotlin.Boolean = true // kotlin.Boolean | When true, indicates that the uploaded image has a watermark.
val altText : kotlin.String = altText_example // kotlin.String | Alt text for the listing image. Max length 500 characters.
try {
    val result : ListingImage = apiInstance.uploadListingImage(shopId, listingId, image, listingImageId, rank, overwrite, isWatermarked, altText)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingImageApi#uploadListingImage")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingImageApi#uploadListingImage")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **image** | **io.ktor.client.request.forms.FormPart&lt;io.ktor.client.request.forms.InputProvider&gt;**| The file name string of a file to upload | [optional] |
| **listingImageId** | **kotlin.Long**| The numeric ID of the primary [listing image](/documentation/reference#tag/ShopListing-Image) for this transaction. | [optional] |
| **rank** | **kotlin.Int**| The positive non-zero numeric position in the images displayed in a listing, with rank 1 images appearing in the left-most position in a listing. | [optional] [default to 1] |
| **overwrite** | **kotlin.Boolean**| When true, this request replaces the existing image at a given rank. | [optional] [default to false] |
| **isWatermarked** | **kotlin.Boolean**| When true, indicates that the uploaded image has a watermark. | [optional] [default to false] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **altText** | **kotlin.String**| Alt text for the listing image. Max length 500 characters. | [optional] [default to &quot;&quot;] |

### Return type

[**ListingImage**](ListingImage.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json

