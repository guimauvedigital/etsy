# ShopListingVideoApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteListingVideo**](ShopListingVideoApi.md#deleteListingVideo) | **DELETE** /v3/application/shops/{shop_id}/listings/{listing_id}/videos/{video_id} |  |
| [**getListingVideo**](ShopListingVideoApi.md#getListingVideo) | **GET** /v3/application/listings/{listing_id}/videos/{video_id} |  |
| [**getListingVideos**](ShopListingVideoApi.md#getListingVideos) | **GET** /v3/application/listings/{listing_id}/videos |  |
| [**uploadListingVideo**](ShopListingVideoApi.md#uploadListingVideo) | **POST** /v3/application/shops/{shop_id}/listings/{listing_id}/videos |  |


<a id="deleteListingVideo"></a>
# **deleteListingVideo**
> deleteListingVideo(shopId, listingId, videoId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 endpoint to delete a listing video. A copy of the video remains on our servers, and so a deleted video may be re-associated with the listing without re-uploading the original video; see uploadListingVideo.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingVideoApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val videoId : kotlin.Long = 789 // kotlin.Long | The unique ID of a video associated with a listing.
try {
    apiInstance.deleteListingVideo(shopId, listingId, videoId)
} catch (e: ClientException) {
    println("4xx response calling ShopListingVideoApi#deleteListingVideo")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingVideoApi#deleteListingVideo")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **videoId** | **kotlin.Long**| The unique ID of a video associated with a listing. | |

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

<a id="getListingVideo"></a>
# **getListingVideo**
> ListingVideo getListingVideo(videoId, listingId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a single video associated with the given listing. Requesting a video from a listing returns an empty result.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingVideoApi()
val videoId : kotlin.Long = 789 // kotlin.Long | The unique ID of a video associated with a listing.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
try {
    val result : ListingVideo = apiInstance.getListingVideo(videoId, listingId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingVideoApi#getListingVideo")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingVideoApi#getListingVideo")
    e.printStackTrace()
}
```

### Parameters
| **videoId** | **kotlin.Long**| The unique ID of a video associated with a listing. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |

### Return type

[**ListingVideo**](ListingVideo.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingVideos"></a>
# **getListingVideos**
> ListingVideos getListingVideos(listingId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves all listing video resources for a listing with a specific listing ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingVideoApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
try {
    val result : ListingVideos = apiInstance.getListingVideos(listingId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingVideoApi#getListingVideos")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingVideoApi#getListingVideos")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |

### Return type

[**ListingVideos**](ListingVideos.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="uploadListingVideo"></a>
# **uploadListingVideo**
> ListingVideo uploadListingVideo(shopId, listingId, videoId, video, name)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Uploads a new video for a listing, or associates an existing video with a specific listing. You must either provide the &#x60;video_id&#x60; of an existing video, or the name and binary file data for a video to upload.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingVideoApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val videoId : kotlin.Long = 789 // kotlin.Long | The unique ID of a video associated with a listing.
val video : io.ktor.client.request.forms.FormPart<io.ktor.client.request.forms.InputProvider> = BINARY_DATA_HERE // io.ktor.client.request.forms.FormPart<io.ktor.client.request.forms.InputProvider> | A video file to upload.
val name : kotlin.String = name_example // kotlin.String | The file name string for the video to upload.
try {
    val result : ListingVideo = apiInstance.uploadListingVideo(shopId, listingId, videoId, video, name)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingVideoApi#uploadListingVideo")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingVideoApi#uploadListingVideo")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **videoId** | **kotlin.Long**| The unique ID of a video associated with a listing. | [optional] |
| **video** | **io.ktor.client.request.forms.FormPart&lt;io.ktor.client.request.forms.InputProvider&gt;**| A video file to upload. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **name** | **kotlin.String**| The file name string for the video to upload. | [optional] |

### Return type

[**ListingVideo**](ListingVideo.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json

