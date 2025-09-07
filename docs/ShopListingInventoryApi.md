# ShopListingInventoryApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getListingInventory**](ShopListingInventoryApi.md#getListingInventory) | **GET** /v3/application/listings/{listing_id}/inventory |  |
| [**updateListingInventory**](ShopListingInventoryApi.md#updateListingInventory) | **PUT** /v3/application/listings/{listing_id}/inventory |  |


<a id="getListingInventory"></a>
# **getListingInventory**
> ListingInventoryWithAssociations getListingInventory(listingId, showDeleted, includes, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves the inventory record for a listing. Listings you did not edit using the Etsy.com inventory tools have no inventory records. This endpoint returns SKU data if you are the owner of the inventory records being fetched.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingInventoryApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val showDeleted : kotlin.Boolean = true // kotlin.Boolean | A boolean value for inventory whether to include deleted products and their offerings. Default value is false.
val includes : kotlin.String = includes_example // kotlin.String | An enumerated string that attaches a valid association. Default value is null.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ListingInventoryWithAssociations = apiInstance.getListingInventory(listingId, showDeleted, includes, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingInventoryApi#getListingInventory")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingInventoryApi#getListingInventory")
    e.printStackTrace()
}
```

### Parameters
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **showDeleted** | **kotlin.Boolean**| A boolean value for inventory whether to include deleted products and their offerings. Default value is false. | [optional] |
| **includes** | **kotlin.String**| An enumerated string that attaches a valid association. Default value is null. | [optional] [enum: Listing] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ListingInventoryWithAssociations**](ListingInventoryWithAssociations.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateListingInventory"></a>
# **updateListingInventory**
> ListingInventory updateListingInventory(listingId, legacy, updateListingInventoryRequest)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates the inventory for a listing identified by a listing ID. The update fails if the supplied values for product sku, offering quantity, and/or price are incompatible with values in &#x60;*_on_property_*&#x60; fields. When setting a price, assign a float equal to amount divided by divisor as specified in the Money resource.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingInventoryApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
val updateListingInventoryRequest : UpdateListingInventoryRequest =  // UpdateListingInventoryRequest | 
try {
    val result : ListingInventory = apiInstance.updateListingInventory(listingId, legacy, updateListingInventoryRequest)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingInventoryApi#updateListingInventory")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingInventoryApi#updateListingInventory")
    e.printStackTrace()
}
```

### Parameters
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **updateListingInventoryRequest** | [**UpdateListingInventoryRequest**](UpdateListingInventoryRequest.md)|  | [optional] |

### Return type

[**ListingInventory**](ListingInventory.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

