# ReviewApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getReviewsByListing**](ReviewApi.md#getReviewsByListing) | **GET** /v3/application/listings/{listing_id}/reviews |  |
| [**getReviewsByShop**](ReviewApi.md#getReviewsByShop) | **GET** /v3/application/shops/{shop_id}/reviews |  |


<a id="getReviewsByListing"></a>
# **getReviewsByListing**
> ListingReviews getReviewsByListing(listingId, limit, offset, minCreated, maxCreated)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 to retrieve the reviews for a listing given its ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ReviewApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
val minCreated : kotlin.Int = 56 // kotlin.Int | The earliest unix timestamp for when a record was created.
val maxCreated : kotlin.Int = 56 // kotlin.Int | The latest unix timestamp for when a record was created.
try {
    val result : ListingReviews = apiInstance.getReviewsByListing(listingId, limit, offset, minCreated, maxCreated)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ReviewApi#getReviewsByListing")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ReviewApi#getReviewsByListing")
    e.printStackTrace()
}
```

### Parameters
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |
| **minCreated** | **kotlin.Int**| The earliest unix timestamp for when a record was created. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **maxCreated** | **kotlin.Int**| The latest unix timestamp for when a record was created. | [optional] |

### Return type

[**ListingReviews**](ListingReviews.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getReviewsByShop"></a>
# **getReviewsByShop**
> TransactionReviews getReviewsByShop(shopId, limit, offset, minCreated, maxCreated)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 to retrieve the reviews from a shop given its ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ReviewApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
val minCreated : kotlin.Int = 56 // kotlin.Int | The earliest unix timestamp for when a record was created.
val maxCreated : kotlin.Int = 56 // kotlin.Int | The latest unix timestamp for when a record was created.
try {
    val result : TransactionReviews = apiInstance.getReviewsByShop(shopId, limit, offset, minCreated, maxCreated)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ReviewApi#getReviewsByShop")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ReviewApi#getReviewsByShop")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |
| **minCreated** | **kotlin.Int**| The earliest unix timestamp for when a record was created. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **maxCreated** | **kotlin.Int**| The latest unix timestamp for when a record was created. | [optional] |

### Return type

[**TransactionReviews**](TransactionReviews.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

