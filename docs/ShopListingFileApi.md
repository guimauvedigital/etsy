# ShopListingFileApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteListingFile**](ShopListingFileApi.md#deleteListingFile) | **DELETE** /v3/application/shops/{shop_id}/listings/{listing_id}/files/{listing_file_id} |  |
| [**getAllListingFiles**](ShopListingFileApi.md#getAllListingFiles) | **GET** /v3/application/shops/{shop_id}/listings/{listing_id}/files |  |
| [**getListingFile**](ShopListingFileApi.md#getListingFile) | **GET** /v3/application/shops/{shop_id}/listings/{listing_id}/files/{listing_file_id} |  |
| [**uploadListingFile**](ShopListingFileApi.md#uploadListingFile) | **POST** /v3/application/shops/{shop_id}/listings/{listing_id}/files |  |


<a id="deleteListingFile"></a>
# **deleteListingFile**
> deleteListingFile(shopId, listingId, listingFileId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Deletes a file from a specific listing. When you delete the final file for a digital listing, the listing converts into a physical listing. The response to a delete request returns a list of the remaining file records associated with the given listing.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingFileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val listingFileId : kotlin.Long = 789 // kotlin.Long | The unique numeric ID of a file associated with a digital listing.
try {
    apiInstance.deleteListingFile(shopId, listingId, listingFileId)
} catch (e: ClientException) {
    println("4xx response calling ShopListingFileApi#deleteListingFile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingFileApi#deleteListingFile")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingFileId** | **kotlin.Long**| The unique numeric ID of a file associated with a digital listing. | |

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

<a id="getAllListingFiles"></a>
# **getAllListingFiles**
> ShopListingFiles getAllListingFiles(listingId, shopId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves all the files associated with the given digital listing. Requesting files from a physical listing returns an empty result.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingFileApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
try {
    val result : ShopListingFiles = apiInstance.getAllListingFiles(listingId, shopId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingFileApi#getAllListingFiles")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingFileApi#getAllListingFiles")
    e.printStackTrace()
}
```

### Parameters
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |

### Return type

[**ShopListingFiles**](ShopListingFiles.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingFile"></a>
# **getListingFile**
> ShopListingFile getListingFile(shopId, listingId, listingFileId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a single file associated with the given digital listing. Requesting a file from a physical listing returns an empty result.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingFileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val listingFileId : kotlin.Long = 789 // kotlin.Long | The unique numeric ID of a file associated with a digital listing.
try {
    val result : ShopListingFile = apiInstance.getListingFile(shopId, listingId, listingFileId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingFileApi#getListingFile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingFileApi#getListingFile")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingFileId** | **kotlin.Long**| The unique numeric ID of a file associated with a digital listing. | |

### Return type

[**ShopListingFile**](ShopListingFile.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="uploadListingFile"></a>
# **uploadListingFile**
> ShopListingFile uploadListingFile(shopId, listingId, listingFileId, file, name, rank)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Uploads a new file for a digital listing, or associates an existing file with a specific listing. You must either provide the &#x60;listing_file_id&#x60; of an existing file, or the name and binary file data for a file to upload. Associating an existing file to a physical listing converts the physical listing into a digital listing, which removes all shipping costs and any product and inventory variations.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingFileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val listingFileId : kotlin.Long = 789 // kotlin.Long | The unique numeric ID of a file associated with a digital listing.
val file : io.ktor.client.request.forms.FormPart<io.ktor.client.request.forms.InputProvider> = BINARY_DATA_HERE // io.ktor.client.request.forms.FormPart<io.ktor.client.request.forms.InputProvider> | A binary file to upload.
val name : kotlin.String = name_example // kotlin.String | The file name string of a file to upload
val rank : kotlin.Long = 789 // kotlin.Long | The positive non-zero numeric position in the images displayed in a listing, with rank 1 images appearing in the left-most position in a listing.
try {
    val result : ShopListingFile = apiInstance.uploadListingFile(shopId, listingId, listingFileId, file, name, rank)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingFileApi#uploadListingFile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingFileApi#uploadListingFile")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **listingFileId** | **kotlin.Long**| The unique numeric ID of a file associated with a digital listing. | [optional] |
| **file** | **io.ktor.client.request.forms.FormPart&lt;io.ktor.client.request.forms.InputProvider&gt;**| A binary file to upload. | [optional] |
| **name** | **kotlin.String**| The file name string of a file to upload | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **rank** | **kotlin.Long**| The positive non-zero numeric position in the images displayed in a listing, with rank 1 images appearing in the left-most position in a listing. | [optional] [default to 1L] |

### Return type

[**ShopListingFile**](ShopListingFile.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json

