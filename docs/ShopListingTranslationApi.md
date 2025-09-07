# ShopListingTranslationApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createListingTranslation**](ShopListingTranslationApi.md#createListingTranslation) | **POST** /v3/application/shops/{shop_id}/listings/{listing_id}/translations/{language} |  |
| [**getListingTranslation**](ShopListingTranslationApi.md#getListingTranslation) | **GET** /v3/application/shops/{shop_id}/listings/{listing_id}/translations/{language} |  |
| [**updateListingTranslation**](ShopListingTranslationApi.md#updateListingTranslation) | **PUT** /v3/application/shops/{shop_id}/listings/{listing_id}/translations/{language} |  |


<a id="createListingTranslation"></a>
# **createListingTranslation**
> ListingTranslation createListingTranslation(shopId, listingId, language, title, description, tags)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Creates a ListingTranslation by listing_id and language

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingTranslationApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val language : kotlin.String = language_example // kotlin.String | The IETF language tag for the language of this translation. Ex: `de`, `en`, `es`, `fr`, `it`, `ja`, `nl`, `pl`, `pt`.
val title : kotlin.String = title_example // kotlin.String | The title of the Listing of this Translation.
val description : kotlin.String = description_example // kotlin.String | The description of the Listing of this Translation.
val tags : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | The tags of the Listing of this Translation.
try {
    val result : ListingTranslation = apiInstance.createListingTranslation(shopId, listingId, language, title, description, tags)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingTranslationApi#createListingTranslation")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingTranslationApi#createListingTranslation")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **language** | **kotlin.String**| The IETF language tag for the language of this translation. Ex: &#x60;de&#x60;, &#x60;en&#x60;, &#x60;es&#x60;, &#x60;fr&#x60;, &#x60;it&#x60;, &#x60;ja&#x60;, &#x60;nl&#x60;, &#x60;pl&#x60;, &#x60;pt&#x60;. | |
| **title** | **kotlin.String**| The title of the Listing of this Translation. | |
| **description** | **kotlin.String**| The description of the Listing of this Translation. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **tags** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| The tags of the Listing of this Translation. | [optional] |

### Return type

[**ListingTranslation**](ListingTranslation.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="getListingTranslation"></a>
# **getListingTranslation**
> ListingTranslation getListingTranslation(shopId, listingId, language)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Get a Translation for a Listing in the given language

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingTranslationApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val language : kotlin.String = language_example // kotlin.String | The IETF language tag for the language of this translation. Ex: `de`, `en`, `es`, `fr`, `it`, `ja`, `nl`, `pl`, `pt`.
try {
    val result : ListingTranslation = apiInstance.getListingTranslation(shopId, listingId, language)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingTranslationApi#getListingTranslation")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingTranslationApi#getListingTranslation")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **language** | **kotlin.String**| The IETF language tag for the language of this translation. Ex: &#x60;de&#x60;, &#x60;en&#x60;, &#x60;es&#x60;, &#x60;fr&#x60;, &#x60;it&#x60;, &#x60;ja&#x60;, &#x60;nl&#x60;, &#x60;pl&#x60;, &#x60;pt&#x60;. | |

### Return type

[**ListingTranslation**](ListingTranslation.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateListingTranslation"></a>
# **updateListingTranslation**
> ListingTranslation updateListingTranslation(shopId, listingId, language, title, description, tags)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates a ListingTranslation by listing_id and language

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingTranslationApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val language : kotlin.String = language_example // kotlin.String | The IETF language tag for the language of this translation. Ex: `de`, `en`, `es`, `fr`, `it`, `ja`, `nl`, `pl`, `pt`.
val title : kotlin.String = title_example // kotlin.String | The title of the Listing of this Translation.
val description : kotlin.String = description_example // kotlin.String | The description of the Listing of this Translation.
val tags : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | The tags of the Listing of this Translation.
try {
    val result : ListingTranslation = apiInstance.updateListingTranslation(shopId, listingId, language, title, description, tags)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingTranslationApi#updateListingTranslation")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingTranslationApi#updateListingTranslation")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **language** | **kotlin.String**| The IETF language tag for the language of this translation. Ex: &#x60;de&#x60;, &#x60;en&#x60;, &#x60;es&#x60;, &#x60;fr&#x60;, &#x60;it&#x60;, &#x60;ja&#x60;, &#x60;nl&#x60;, &#x60;pl&#x60;, &#x60;pt&#x60;. | |
| **title** | **kotlin.String**| The title of the Listing of this Translation. | |
| **description** | **kotlin.String**| The description of the Listing of this Translation. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **tags** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| The tags of the Listing of this Translation. | [optional] |

### Return type

[**ListingTranslation**](ListingTranslation.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

