# ShopListingApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createDraftListing**](ShopListingApi.md#createDraftListing) | **POST** /v3/application/shops/{shop_id}/listings |  |
| [**deleteListing**](ShopListingApi.md#deleteListing) | **DELETE** /v3/application/listings/{listing_id} |  |
| [**deleteListingProperty**](ShopListingApi.md#deleteListingProperty) | **DELETE** /v3/application/shops/{shop_id}/listings/{listing_id}/properties/{property_id} |  |
| [**findAllActiveListingsByShop**](ShopListingApi.md#findAllActiveListingsByShop) | **GET** /v3/application/shops/{shop_id}/listings/active |  |
| [**findAllListingsActive**](ShopListingApi.md#findAllListingsActive) | **GET** /v3/application/listings/active |  |
| [**getFeaturedListingsByShop**](ShopListingApi.md#getFeaturedListingsByShop) | **GET** /v3/application/shops/{shop_id}/listings/featured |  |
| [**getListing**](ShopListingApi.md#getListing) | **GET** /v3/application/listings/{listing_id} |  |
| [**getListingProperties**](ShopListingApi.md#getListingProperties) | **GET** /v3/application/shops/{shop_id}/listings/{listing_id}/properties |  |
| [**getListingProperty**](ShopListingApi.md#getListingProperty) | **GET** /v3/application/listings/{listing_id}/properties/{property_id} |  |
| [**getListingsByListingIds**](ShopListingApi.md#getListingsByListingIds) | **GET** /v3/application/listings/batch |  |
| [**getListingsByShop**](ShopListingApi.md#getListingsByShop) | **GET** /v3/application/shops/{shop_id}/listings |  |
| [**getListingsByShopReceipt**](ShopListingApi.md#getListingsByShopReceipt) | **GET** /v3/application/shops/{shop_id}/receipts/{receipt_id}/listings |  |
| [**getListingsByShopReturnPolicy**](ShopListingApi.md#getListingsByShopReturnPolicy) | **GET** /v3/application/shops/{shop_id}/policies/return/{return_policy_id}/listings |  |
| [**getListingsByShopSectionId**](ShopListingApi.md#getListingsByShopSectionId) | **GET** /v3/application/shops/{shop_id}/shop-sections/listings |  |
| [**updateListing**](ShopListingApi.md#updateListing) | **PATCH** /v3/application/shops/{shop_id}/listings/{listing_id} |  |
| [**updateListingProperty**](ShopListingApi.md#updateListingProperty) | **PUT** /v3/application/shops/{shop_id}/listings/{listing_id}/properties/{property_id} |  |


<a id="createDraftListing"></a>
# **createDraftListing**
> ShopListing createDraftListing(shopId, quantity, title, description, price, whoMade, whenMade, taxonomyId, legacy, shippingProfileId, returnPolicyId, materials, shopSectionId, processingMin, processingMax, readinessStateId, tags, styles, itemWeight, itemLength, itemWidth, itemHeight, itemWeightUnit, itemDimensionsUnit, isPersonalizable, personalizationIsRequired, personalizationCharCountMax, personalizationInstructions, productionPartnerIds, imageIds, isSupply, isCustomizable, shouldAutoRenew, isTaxable, type)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Creates a physical draft [listing](/documentation/reference#tag/ShopListing) product in a shop on the Etsy channel.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val quantity : kotlin.Int = 56 // kotlin.Int | The positive non-zero number of products available for purchase in the listing. Note: The listing quantity is the sum of available offering quantities. You can request the quantities for individual offerings from the ListingInventory resource using the [getListingInventory](/documentation/reference#operation/getListingInventory) endpoint.
val title : kotlin.String = title_example // kotlin.String | The listing's title string. When creating or updating a listing, valid title strings contain only letters, numbers, punctuation marks, mathematical symbols, whitespace characters, ™, ©, and ®. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{P}\\\\p{Sm}\\\\p{Zs}™©®]/u) You can only use the %, :, & and + characters once each.
val description : kotlin.String = description_example // kotlin.String | A description string of the product for sale in the listing.
val price : kotlin.Float = 3.4 // kotlin.Float | The positive non-zero price of the product. (Sold product listings are private) Note: The price is the minimum possible price. The [`getListingInventory`](/documentation/reference/#operation/getListingInventory) method requests exact prices for available offerings.
val whoMade : kotlin.String = whoMade_example // kotlin.String | An enumerated string indicating who made the product. Helps buyers locate the listing under the Handmade heading. Requires 'is_supply' and 'when_made'.
val whenMade : kotlin.String = whenMade_example // kotlin.String | An enumerated string for the era in which the maker made the product in this listing. Helps buyers locate the listing under the Vintage heading. Requires 'is_supply' and 'who_made'.
val taxonomyId : kotlin.Long = 789 // kotlin.Long | The numerical taxonomy ID of the listing. See [SellerTaxonomy](/documentation/reference#tag/SellerTaxonomy) and [BuyerTaxonomy](/documentation/reference#tag/BuyerTaxonomy) for more information.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
val returnPolicyId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies).
val materials : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | A list of material strings for materials used in the product. Valid materials strings contain only letters, numbers, and whitespace characters. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}]/u) Default value is null.
val shopSectionId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shop section](/documentation/reference#tag/Shop-Section) for this listing. Default value is null.
val processingMin : kotlin.Int = 56 // kotlin.Int | The minimum number of days required to process this listing. Default value is null.
val processingMax : kotlin.Int = 56 // kotlin.Int | The maximum number of days required to process this listing. Default value is null.
val readinessStateId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is `physical`.
val tags : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | A comma-separated list of tag strings for the listing. When creating or updating a listing, valid tag strings contain only letters, numbers, whitespace characters, -, ', ™, ©, and ®. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}\\\\-'™©®]/u) Default value is null.
val styles : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | An array of style strings for this listing, each of which is free-form text string such as \\\"Formal\\\", or \\\"Steampunk\\\". When creating or updating a listing, the listing may have up to two styles. Valid style strings contain only letters, numbers, and whitespace characters. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}]/u) Default value is null.
val itemWeight : kotlin.Float = 3.4 // kotlin.Float | The numeric weight of the product measured in units set in 'item_weight_unit'. Default value is null. If set, the value must be greater than 0.
val itemLength : kotlin.Float = 3.4 // kotlin.Float | The numeric length of the product measured in units set in 'item_dimensions_unit'. Default value is null. If set, the value must be greater than 0.
val itemWidth : kotlin.Float = 3.4 // kotlin.Float | The numeric width of the product measured in units set in 'item_dimensions_unit'. Default value is null. If set, the value must be greater than 0.
val itemHeight : kotlin.Float = 3.4 // kotlin.Float | The numeric height of the product measured in units set in 'item_dimensions_unit'. Default value is null. If set, the value must be greater than 0.
val itemWeightUnit : kotlin.String = itemWeightUnit_example // kotlin.String | A string defining the units used to measure the weight of the product. Default value is null.
val itemDimensionsUnit : kotlin.String = itemDimensionsUnit_example // kotlin.String | A string defining the units used to measure the dimensions of the product. Default value is null.
val isPersonalizable : kotlin.Boolean = true // kotlin.Boolean | When true, this listing is personalizable. The default value is null.
val personalizationIsRequired : kotlin.Boolean = true // kotlin.Boolean | When true, this listing requires personalization. The default value is null. Will only change if is_personalizable is 'true'.
val personalizationCharCountMax : kotlin.Int = 56 // kotlin.Int | This is an integer value representing the maximum length for the personalization message entered by the buyer. Will only change if is_personalizable is 'true'.
val personalizationInstructions : kotlin.String = personalizationInstructions_example // kotlin.String | A string representing instructions for the buyer to enter the personalization. Will only change if is_personalizable is 'true'.
val productionPartnerIds : kotlin.collections.List<kotlin.Long> =  // kotlin.collections.List<kotlin.Long> | An array of unique IDs of production partner ids.
val imageIds : kotlin.collections.List<kotlin.Long> =  // kotlin.collections.List<kotlin.Long> | An array of numeric image IDs of the images in a listing, which can include up to 10 images.
val isSupply : kotlin.Boolean = true // kotlin.Boolean | When true, tags the listing as a supply product, else indicates that it's a finished product. Helps buyers locate the listing under the Supplies heading. Requires 'who_made' and 'when_made'.
val isCustomizable : kotlin.Boolean = true // kotlin.Boolean | When true, a buyer may contact the seller for a customized order. The default value is true when a shop accepts custom orders. Does not apply to shops that do not accept custom orders.
val shouldAutoRenew : kotlin.Boolean = true // kotlin.Boolean | When true, renews a listing for four months upon expiration.
val isTaxable : kotlin.Boolean = true // kotlin.Boolean | When true, applicable [shop](/documentation/reference#tag/Shop) tax rates apply to this listing at checkout.
val type : kotlin.String = type_example // kotlin.String | An enumerated type string that indicates whether the listing is physical or a digital download.
try {
    val result : ShopListing = apiInstance.createDraftListing(shopId, quantity, title, description, price, whoMade, whenMade, taxonomyId, legacy, shippingProfileId, returnPolicyId, materials, shopSectionId, processingMin, processingMax, readinessStateId, tags, styles, itemWeight, itemLength, itemWidth, itemHeight, itemWeightUnit, itemDimensionsUnit, isPersonalizable, personalizationIsRequired, personalizationCharCountMax, personalizationInstructions, productionPartnerIds, imageIds, isSupply, isCustomizable, shouldAutoRenew, isTaxable, type)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#createDraftListing")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#createDraftListing")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **quantity** | **kotlin.Int**| The positive non-zero number of products available for purchase in the listing. Note: The listing quantity is the sum of available offering quantities. You can request the quantities for individual offerings from the ListingInventory resource using the [getListingInventory](/documentation/reference#operation/getListingInventory) endpoint. | |
| **title** | **kotlin.String**| The listing&#39;s title string. When creating or updating a listing, valid title strings contain only letters, numbers, punctuation marks, mathematical symbols, whitespace characters, ™, ©, and ®. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{P}\\\\p{Sm}\\\\p{Zs}™©®]/u) You can only use the %, :, &amp; and + characters once each. | |
| **description** | **kotlin.String**| A description string of the product for sale in the listing. | |
| **price** | **kotlin.Float**| The positive non-zero price of the product. (Sold product listings are private) Note: The price is the minimum possible price. The [&#x60;getListingInventory&#x60;](/documentation/reference/#operation/getListingInventory) method requests exact prices for available offerings. | |
| **whoMade** | **kotlin.String**| An enumerated string indicating who made the product. Helps buyers locate the listing under the Handmade heading. Requires &#39;is_supply&#39; and &#39;when_made&#39;. | [enum: i_did, someone_else, collective] |
| **whenMade** | **kotlin.String**| An enumerated string for the era in which the maker made the product in this listing. Helps buyers locate the listing under the Vintage heading. Requires &#39;is_supply&#39; and &#39;who_made&#39;. | [enum: made_to_order, 2020_2025, 2010_2019, 2006_2009, before_2006, 2000_2005, 1990s, 1980s, 1970s, 1960s, 1950s, 1940s, 1930s, 1920s, 1910s, 1900s, 1800s, 1700s, before_1700] |
| **taxonomyId** | **kotlin.Long**| The numerical taxonomy ID of the listing. See [SellerTaxonomy](/documentation/reference#tag/SellerTaxonomy) and [BuyerTaxonomy](/documentation/reference#tag/BuyerTaxonomy) for more information. | |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | [optional] |
| **returnPolicyId** | **kotlin.Long**| The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). | [optional] |
| **materials** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| A list of material strings for materials used in the product. Valid materials strings contain only letters, numbers, and whitespace characters. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}]/u) Default value is null. | [optional] |
| **shopSectionId** | **kotlin.Long**| The numeric ID of the [shop section](/documentation/reference#tag/Shop-Section) for this listing. Default value is null. | [optional] |
| **processingMin** | **kotlin.Int**| The minimum number of days required to process this listing. Default value is null. | [optional] |
| **processingMax** | **kotlin.Int**| The maximum number of days required to process this listing. Default value is null. | [optional] |
| **readinessStateId** | **kotlin.Long**| The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is &#x60;physical&#x60;. | [optional] |
| **tags** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| A comma-separated list of tag strings for the listing. When creating or updating a listing, valid tag strings contain only letters, numbers, whitespace characters, -, &#39;, ™, ©, and ®. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}\\\\-&#39;™©®]/u) Default value is null. | [optional] |
| **styles** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| An array of style strings for this listing, each of which is free-form text string such as \\\&quot;Formal\\\&quot;, or \\\&quot;Steampunk\\\&quot;. When creating or updating a listing, the listing may have up to two styles. Valid style strings contain only letters, numbers, and whitespace characters. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}]/u) Default value is null. | [optional] |
| **itemWeight** | **kotlin.Float**| The numeric weight of the product measured in units set in &#39;item_weight_unit&#39;. Default value is null. If set, the value must be greater than 0. | [optional] |
| **itemLength** | **kotlin.Float**| The numeric length of the product measured in units set in &#39;item_dimensions_unit&#39;. Default value is null. If set, the value must be greater than 0. | [optional] |
| **itemWidth** | **kotlin.Float**| The numeric width of the product measured in units set in &#39;item_dimensions_unit&#39;. Default value is null. If set, the value must be greater than 0. | [optional] |
| **itemHeight** | **kotlin.Float**| The numeric height of the product measured in units set in &#39;item_dimensions_unit&#39;. Default value is null. If set, the value must be greater than 0. | [optional] |
| **itemWeightUnit** | **kotlin.String**| A string defining the units used to measure the weight of the product. Default value is null. | [optional] [enum: oz, lb, g, kg] |
| **itemDimensionsUnit** | **kotlin.String**| A string defining the units used to measure the dimensions of the product. Default value is null. | [optional] [enum: in, ft, mm, cm, m, yd, inches] |
| **isPersonalizable** | **kotlin.Boolean**| When true, this listing is personalizable. The default value is null. | [optional] |
| **personalizationIsRequired** | **kotlin.Boolean**| When true, this listing requires personalization. The default value is null. Will only change if is_personalizable is &#39;true&#39;. | [optional] |
| **personalizationCharCountMax** | **kotlin.Int**| This is an integer value representing the maximum length for the personalization message entered by the buyer. Will only change if is_personalizable is &#39;true&#39;. | [optional] |
| **personalizationInstructions** | **kotlin.String**| A string representing instructions for the buyer to enter the personalization. Will only change if is_personalizable is &#39;true&#39;. | [optional] |
| **productionPartnerIds** | [**kotlin.collections.List&lt;kotlin.Long&gt;**](kotlin.Long.md)| An array of unique IDs of production partner ids. | [optional] |
| **imageIds** | [**kotlin.collections.List&lt;kotlin.Long&gt;**](kotlin.Long.md)| An array of numeric image IDs of the images in a listing, which can include up to 10 images. | [optional] |
| **isSupply** | **kotlin.Boolean**| When true, tags the listing as a supply product, else indicates that it&#39;s a finished product. Helps buyers locate the listing under the Supplies heading. Requires &#39;who_made&#39; and &#39;when_made&#39;. | [optional] |
| **isCustomizable** | **kotlin.Boolean**| When true, a buyer may contact the seller for a customized order. The default value is true when a shop accepts custom orders. Does not apply to shops that do not accept custom orders. | [optional] |
| **shouldAutoRenew** | **kotlin.Boolean**| When true, renews a listing for four months upon expiration. | [optional] |
| **isTaxable** | **kotlin.Boolean**| When true, applicable [shop](/documentation/reference#tag/Shop) tax rates apply to this listing at checkout. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **type** | **kotlin.String**| An enumerated type string that indicates whether the listing is physical or a digital download. | [optional] [enum: physical, download, both] |

### Return type

[**ShopListing**](ShopListing.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="deleteListing"></a>
# **deleteListing**
> deleteListing(listingId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 endpoint to delete a ShopListing. A ShopListing can be deleted only if the state is one of the following:  SOLD_OUT, DRAFT, EXPIRED, INACTIVE, ACTIVE and is_available or ACTIVE and has seller flags:  SUPRESSED (frozen), VACATION, CUSTOM_SHOPS (pattern), SELL_ON_FACEBOOK

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
try {
    apiInstance.deleteListing(listingId)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#deleteListing")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#deleteListing")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |

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

<a id="deleteListingProperty"></a>
# **deleteListingProperty**
> deleteListingProperty(shopId, listingId, propertyId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Deletes a property for a Listing.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val propertyId : kotlin.Long = 789 // kotlin.Long | The unique ID of an Etsy [listing property](/documentation/reference#operation/getListingProperties).
try {
    apiInstance.deleteListingProperty(shopId, listingId, propertyId)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#deleteListingProperty")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#deleteListingProperty")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **propertyId** | **kotlin.Long**| The unique ID of an Etsy [listing property](/documentation/reference#operation/getListingProperties). | |

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

<a id="findAllActiveListingsByShop"></a>
# **findAllActiveListingsByShop**
> ShopListings findAllActiveListingsByShop(shopId, limit, sortOn, sortOrder, offset, keywords, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a list of all active listings on Etsy in a specific shop, paginated by listing creation date.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val sortOn : kotlin.String = sortOn_example // kotlin.String | The value to sort a search result of listings on. NOTES: a) `sort_on` only works when combined with one of the search options (keywords, region, etc.). b) when using `score` the returned results will always be in _descending_ order, regardless of the `sort_order` parameter.
val sortOrder : kotlin.String = sortOrder_example // kotlin.String | The ascending(up) or descending(down) order to sort listings by. NOTE: sort_order only works when combined with one of the search options (keywords, region, etc.).
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
val keywords : kotlin.String = keywords_example // kotlin.String | Search term or phrase that must appear in all results.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ShopListings = apiInstance.findAllActiveListingsByShop(shopId, limit, sortOn, sortOrder, offset, keywords, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#findAllActiveListingsByShop")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#findAllActiveListingsByShop")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| **sortOn** | **kotlin.String**| The value to sort a search result of listings on. NOTES: a) &#x60;sort_on&#x60; only works when combined with one of the search options (keywords, region, etc.). b) when using &#x60;score&#x60; the returned results will always be in _descending_ order, regardless of the &#x60;sort_order&#x60; parameter. | [optional] [default to created] [enum: created, price, updated, score] |
| **sortOrder** | **kotlin.String**| The ascending(up) or descending(down) order to sort listings by. NOTE: sort_order only works when combined with one of the search options (keywords, region, etc.). | [optional] [default to desc] [enum: asc, ascending, desc, descending, up, down] |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |
| **keywords** | **kotlin.String**| Search term or phrase that must appear in all results. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ShopListings**](ShopListings.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="findAllListingsActive"></a>
# **findAllListingsActive**
> ShopListings findAllListingsActive(limit, offset, keywords, sortOn, sortOrder, minPrice, maxPrice, taxonomyId, shopLocation, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  A list of all active listings on Etsy paginated by their creation date. Without sort_order listings will be returned newest-first by default.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
val keywords : kotlin.String = keywords_example // kotlin.String | Search term or phrase that must appear in all results.
val sortOn : kotlin.String = sortOn_example // kotlin.String | The value to sort a search result of listings on. NOTES: a) `sort_on` only works when combined with one of the search options (keywords, region, etc.). b) when using `score` the returned results will always be in _descending_ order, regardless of the `sort_order` parameter.
val sortOrder : kotlin.String = sortOrder_example // kotlin.String | The ascending(up) or descending(down) order to sort listings by. NOTE: sort_order only works when combined with one of the search options (keywords, region, etc.).
val minPrice : kotlin.Float = 3.4 // kotlin.Float | The minimum price of listings to be returned by a search result.
val maxPrice : kotlin.Float = 3.4 // kotlin.Float | The maximum price of listings to be returned by a search result.
val taxonomyId : kotlin.Long = 789 // kotlin.Long | The numerical taxonomy ID of the listing. See [SellerTaxonomy](/documentation/reference#tag/SellerTaxonomy) and [BuyerTaxonomy](/documentation/reference#tag/BuyerTaxonomy) for more information.
val shopLocation : kotlin.String = shopLocation_example // kotlin.String | Filters by shop location. If location cannot be parsed, Etsy responds with an error.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ShopListings = apiInstance.findAllListingsActive(limit, offset, keywords, sortOn, sortOrder, minPrice, maxPrice, taxonomyId, shopLocation, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#findAllListingsActive")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#findAllListingsActive")
    e.printStackTrace()
}
```

### Parameters
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |
| **keywords** | **kotlin.String**| Search term or phrase that must appear in all results. | [optional] |
| **sortOn** | **kotlin.String**| The value to sort a search result of listings on. NOTES: a) &#x60;sort_on&#x60; only works when combined with one of the search options (keywords, region, etc.). b) when using &#x60;score&#x60; the returned results will always be in _descending_ order, regardless of the &#x60;sort_order&#x60; parameter. | [optional] [default to created] [enum: created, price, updated, score] |
| **sortOrder** | **kotlin.String**| The ascending(up) or descending(down) order to sort listings by. NOTE: sort_order only works when combined with one of the search options (keywords, region, etc.). | [optional] [default to desc] [enum: asc, ascending, desc, descending, up, down] |
| **minPrice** | **kotlin.Float**| The minimum price of listings to be returned by a search result. | [optional] |
| **maxPrice** | **kotlin.Float**| The maximum price of listings to be returned by a search result. | [optional] |
| **taxonomyId** | **kotlin.Long**| The numerical taxonomy ID of the listing. See [SellerTaxonomy](/documentation/reference#tag/SellerTaxonomy) and [BuyerTaxonomy](/documentation/reference#tag/BuyerTaxonomy) for more information. | [optional] |
| **shopLocation** | **kotlin.String**| Filters by shop location. If location cannot be parsed, Etsy responds with an error. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ShopListings**](ShopListings.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getFeaturedListingsByShop"></a>
# **getFeaturedListingsByShop**
> ShopListings getFeaturedListingsByShop(shopId, limit, offset)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves Listings associated to a Shop that are featured.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
try {
    val result : ShopListings = apiInstance.getFeaturedListingsByShop(shopId, limit, offset)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#getFeaturedListingsByShop")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#getFeaturedListingsByShop")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |

### Return type

[**ShopListings**](ShopListings.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListing"></a>
# **getListing**
> ShopListingWithAssociations getListing(listingId, includes, language, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a listing record by listing ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val includes : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | An enumerated string that attaches a valid association. Acceptable inputs are 'Shipping', 'Shop', 'Images', 'User', 'Translations' and 'Inventory'.
val language : kotlin.String = language_example // kotlin.String | The IETF language tag for the language of this translation. Ex: `de`, `en`, `es`, `fr`, `it`, `ja`, `nl`, `pl`, `pt`.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ShopListingWithAssociations = apiInstance.getListing(listingId, includes, language, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#getListing")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#getListing")
    e.printStackTrace()
}
```

### Parameters
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **includes** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| An enumerated string that attaches a valid association. Acceptable inputs are &#39;Shipping&#39;, &#39;Shop&#39;, &#39;Images&#39;, &#39;User&#39;, &#39;Translations&#39; and &#39;Inventory&#39;. | [optional] [enum: Shipping, Images, Shop, User, Translations, Inventory, Videos] |
| **language** | **kotlin.String**| The IETF language tag for the language of this translation. Ex: &#x60;de&#x60;, &#x60;en&#x60;, &#x60;es&#x60;, &#x60;fr&#x60;, &#x60;it&#x60;, &#x60;ja&#x60;, &#x60;nl&#x60;, &#x60;pl&#x60;, &#x60;pt&#x60;. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ShopListingWithAssociations**](ShopListingWithAssociations.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingProperties"></a>
# **getListingProperties**
> ListingPropertyValues getListingProperties(shopId, listingId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Get a listing&#39;s properties

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
try {
    val result : ListingPropertyValues = apiInstance.getListingProperties(shopId, listingId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#getListingProperties")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#getListingProperties")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |

### Return type

[**ListingPropertyValues**](ListingPropertyValues.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingProperty"></a>
# **getListingProperty**
> ListingPropertyValue getListingProperty(listingId, propertyId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationTertiary wt-mr-xs-2\&quot;&gt; Feedback only &lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Give feedback&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;Development for this endpoint is in progress. It will only return a 501 response.&lt;/p&gt;&lt;/div&gt;  Retrieves a listing&#39;s property

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val propertyId : kotlin.Long = 789 // kotlin.Long | The unique ID of an Etsy [listing property](/documentation/reference#operation/getListingProperties).
try {
    val result : ListingPropertyValue = apiInstance.getListingProperty(listingId, propertyId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#getListingProperty")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#getListingProperty")
    e.printStackTrace()
}
```

### Parameters
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **propertyId** | **kotlin.Long**| The unique ID of an Etsy [listing property](/documentation/reference#operation/getListingProperties). | |

### Return type

[**ListingPropertyValue**](ListingPropertyValue.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingsByListingIds"></a>
# **getListingsByListingIds**
> ShopListingsWithAssociations getListingsByListingIds(listingIds, includes)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Allows to query multiple listing ids at once. Limit 100 ids maximum per query.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val listingIds : kotlin.collections.List<kotlin.Long> =  // kotlin.collections.List<kotlin.Long> | The list of numeric IDS for the listings in a specific Etsy shop.
val includes : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | An enumerated string that attaches a valid association. Acceptable inputs are 'Shipping', 'Shop', 'Images', 'User', 'Translations' and 'Inventory'.
try {
    val result : ShopListingsWithAssociations = apiInstance.getListingsByListingIds(listingIds, includes)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#getListingsByListingIds")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#getListingsByListingIds")
    e.printStackTrace()
}
```

### Parameters
| **listingIds** | [**kotlin.collections.List&lt;kotlin.Long&gt;**](kotlin.Long.md)| The list of numeric IDS for the listings in a specific Etsy shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **includes** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| An enumerated string that attaches a valid association. Acceptable inputs are &#39;Shipping&#39;, &#39;Shop&#39;, &#39;Images&#39;, &#39;User&#39;, &#39;Translations&#39; and &#39;Inventory&#39;. | [optional] [enum: Shipping, Images, Shop, User, Translations, Inventory, Videos] |

### Return type

[**ShopListingsWithAssociations**](ShopListingsWithAssociations.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingsByShop"></a>
# **getListingsByShop**
> ShopListingsWithAssociations getListingsByShop(shopId, state, limit, offset, sortOn, sortOrder, includes, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Endpoint to list Listings that belong to a Shop. Listings can be filtered using the &#39;state&#39; param.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val state : kotlin.String = state_example // kotlin.String | When _updating_ a listing, this value can be either `active` or `inactive`. Note: Setting a `draft` listing to `active` will also publish the listing on etsy.com and requires that the listing have an image set. Setting a `sold_out` listing to active will update the quantity to 1 and renew the listing on etsy.com.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
val sortOn : kotlin.String = sortOn_example // kotlin.String | The value to sort a search result of listings on. NOTES: a) `sort_on` only works when combined with one of the search options (keywords, region, etc.). b) when using `score` the returned results will always be in _descending_ order, regardless of the `sort_order` parameter.
val sortOrder : kotlin.String = sortOrder_example // kotlin.String | The ascending(up) or descending(down) order to sort listings by. NOTE: sort_order only works when combined with one of the search options (keywords, region, etc.).
val includes : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | An enumerated string that attaches a valid association. Acceptable inputs are 'Shipping', 'Shop', 'Images', 'User', 'Translations' and 'Inventory'.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ShopListingsWithAssociations = apiInstance.getListingsByShop(shopId, state, limit, offset, sortOn, sortOrder, includes, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#getListingsByShop")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#getListingsByShop")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **state** | **kotlin.String**| When _updating_ a listing, this value can be either &#x60;active&#x60; or &#x60;inactive&#x60;. Note: Setting a &#x60;draft&#x60; listing to &#x60;active&#x60; will also publish the listing on etsy.com and requires that the listing have an image set. Setting a &#x60;sold_out&#x60; listing to active will update the quantity to 1 and renew the listing on etsy.com. | [optional] [default to active] [enum: active, inactive, sold_out, draft, expired] |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |
| **sortOn** | **kotlin.String**| The value to sort a search result of listings on. NOTES: a) &#x60;sort_on&#x60; only works when combined with one of the search options (keywords, region, etc.). b) when using &#x60;score&#x60; the returned results will always be in _descending_ order, regardless of the &#x60;sort_order&#x60; parameter. | [optional] [default to created] [enum: created, price, updated, score] |
| **sortOrder** | **kotlin.String**| The ascending(up) or descending(down) order to sort listings by. NOTE: sort_order only works when combined with one of the search options (keywords, region, etc.). | [optional] [default to desc] [enum: asc, ascending, desc, descending, up, down] |
| **includes** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| An enumerated string that attaches a valid association. Acceptable inputs are &#39;Shipping&#39;, &#39;Shop&#39;, &#39;Images&#39;, &#39;User&#39;, &#39;Translations&#39; and &#39;Inventory&#39;. | [optional] [enum: Shipping, Images, Shop, User, Translations, Inventory, Videos] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ShopListingsWithAssociations**](ShopListingsWithAssociations.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingsByShopReceipt"></a>
# **getListingsByShopReceipt**
> ShopListings getListingsByShopReceipt(receiptId, shopId, limit, offset)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Gets all listings associated with a receipt.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val receiptId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction.
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
try {
    val result : ShopListings = apiInstance.getListingsByShopReceipt(receiptId, shopId, limit, offset)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#getListingsByShopReceipt")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#getListingsByShopReceipt")
    e.printStackTrace()
}
```

### Parameters
| **receiptId** | **kotlin.Long**| The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction. | |
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |

### Return type

[**ShopListings**](ShopListings.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingsByShopReturnPolicy"></a>
# **getListingsByShopReturnPolicy**
> ShopListings getListingsByShopReturnPolicy(returnPolicyId, shopId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Gets all listings associated with a Return Policy.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val returnPolicyId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies).
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
try {
    val result : ShopListings = apiInstance.getListingsByShopReturnPolicy(returnPolicyId, shopId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#getListingsByShopReturnPolicy")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#getListingsByShopReturnPolicy")
    e.printStackTrace()
}
```

### Parameters
| **returnPolicyId** | **kotlin.Long**| The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |

### Return type

[**ShopListings**](ShopListings.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getListingsByShopSectionId"></a>
# **getListingsByShopSectionId**
> ShopListings getListingsByShopSectionId(shopId, shopSectionIds, limit, offset, sortOn, sortOrder)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves all the listings from the section of a specific shop.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shopSectionIds : kotlin.collections.List<kotlin.Long> =  // kotlin.collections.List<kotlin.Long> | A list of numeric IDS for all sections in a specific Etsy shop.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
val sortOn : kotlin.String = sortOn_example // kotlin.String | The value to sort a search result of listings on. NOTES: a) `sort_on` only works when combined with one of the search options (keywords, region, etc.). b) when using `score` the returned results will always be in _descending_ order, regardless of the `sort_order` parameter.
val sortOrder : kotlin.String = sortOrder_example // kotlin.String | The ascending(up) or descending(down) order to sort listings by. NOTE: sort_order only works when combined with one of the search options (keywords, region, etc.).
try {
    val result : ShopListings = apiInstance.getListingsByShopSectionId(shopId, shopSectionIds, limit, offset, sortOn, sortOrder)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#getListingsByShopSectionId")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#getListingsByShopSectionId")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **shopSectionIds** | [**kotlin.collections.List&lt;kotlin.Long&gt;**](kotlin.Long.md)| A list of numeric IDS for all sections in a specific Etsy shop. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |
| **sortOn** | **kotlin.String**| The value to sort a search result of listings on. NOTES: a) &#x60;sort_on&#x60; only works when combined with one of the search options (keywords, region, etc.). b) when using &#x60;score&#x60; the returned results will always be in _descending_ order, regardless of the &#x60;sort_order&#x60; parameter. | [optional] [default to created] [enum: created, price, updated, score] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **sortOrder** | **kotlin.String**| The ascending(up) or descending(down) order to sort listings by. NOTE: sort_order only works when combined with one of the search options (keywords, region, etc.). | [optional] [default to desc] [enum: asc, ascending, desc, descending, up, down] |

### Return type

[**ShopListings**](ShopListings.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateListing"></a>
# **updateListing**
> ShopListing updateListing(shopId, listingId, legacy, imageIds, title, description, materials, shouldAutoRenew, shippingProfileId, returnPolicyId, shopSectionId, itemWeight, itemLength, itemWidth, itemHeight, itemWeightUnit, itemDimensionsUnit, isTaxable, taxonomyId, tags, whoMade, whenMade, featuredRank, isPersonalizable, personalizationIsRequired, personalizationCharCountMax, personalizationInstructions, state, isSupply, productionPartnerIds, type)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates a listing, identified by a listing ID, for a specific shop identified by a shop ID. Note that this is a PATCH method type. When activating, or manually renewing a physical listing, the shipping profile referenced by the &#x60;shipping_profile_id&#x60;, and all of its fields, along with its entries and upgrades must be complete and valid. If the shipping profile is not complete and valid, we will throw an exception with an error message that guides the request sender to update whatever data is bad.  Draft digital listings that are not made to order must have a file upload associated with it to be activated. If the listing is made to order, the file upload is not required.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
val imageIds : kotlin.collections.List<kotlin.Long> =  // kotlin.collections.List<kotlin.Long> | An array of numeric image IDs of the images in a listing, which can include up to 10 images.
val title : kotlin.String = title_example // kotlin.String | The listing's title string. When creating or updating a listing, valid title strings contain only letters, numbers, punctuation marks, mathematical symbols, whitespace characters, ™, ©, and ®. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{P}\\\\p{Sm}\\\\p{Zs}™©®]/u) You can only use the %, :, & and + characters once each.
val description : kotlin.String = description_example // kotlin.String | A description string of the product for sale in the listing.
val materials : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | A list of material strings for materials used in the product. Valid materials strings contain only letters, numbers, and whitespace characters. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}]/u) Default value is null.
val shouldAutoRenew : kotlin.Boolean = true // kotlin.Boolean | When true, renews a listing for four months upon expiration.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
val returnPolicyId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). Required for active physical listings. This requirement does not apply to listings of EU-based shops.
val shopSectionId : kotlin.Int = 56 // kotlin.Int | The numeric ID of the [shop section](/documentation/reference#tag/Shop-Section) for this listing. Default value is null.
val itemWeight : kotlin.Float = 3.4 // kotlin.Float | The numeric weight of the product measured in units set in 'item_weight_unit'. Default value is null. If set, the value must be greater than 0.
val itemLength : kotlin.Float = 3.4 // kotlin.Float | The numeric length of the product measured in units set in 'item_dimensions_unit'. Default value is null. If set, the value must be greater than 0.
val itemWidth : kotlin.Float = 3.4 // kotlin.Float | The numeric width of the product measured in units set in 'item_dimensions_unit'. Default value is null. If set, the value must be greater than 0.
val itemHeight : kotlin.Float = 3.4 // kotlin.Float | The numeric height of the product measured in units set in 'item_dimensions_unit'. Default value is null. If set, the value must be greater than 0.
val itemWeightUnit : kotlin.String = itemWeightUnit_example // kotlin.String | A string defining the units used to measure the weight of the product. Default value is null.
val itemDimensionsUnit : kotlin.String = itemDimensionsUnit_example // kotlin.String | A string defining the units used to measure the dimensions of the product. Default value is null.
val isTaxable : kotlin.Boolean = true // kotlin.Boolean | When true, applicable [shop](/documentation/reference#tag/Shop) tax rates apply to this listing at checkout.
val taxonomyId : kotlin.Long = 789 // kotlin.Long | The numerical taxonomy ID of the listing. See [SellerTaxonomy](/documentation/reference#tag/SellerTaxonomy) and [BuyerTaxonomy](/documentation/reference#tag/BuyerTaxonomy) for more information.
val tags : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | A comma-separated list of tag strings for the listing. When creating or updating a listing, valid tag strings contain only letters, numbers, whitespace characters, -, ', ™, ©, and ®. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}\\\\-'™©®]/u) Default value is null.
val whoMade : kotlin.String = whoMade_example // kotlin.String | An enumerated string indicating who made the product. Helps buyers locate the listing under the Handmade heading. Requires 'is_supply' and 'when_made'.
val whenMade : kotlin.String = whenMade_example // kotlin.String | An enumerated string for the era in which the maker made the product in this listing. Helps buyers locate the listing under the Vintage heading. Requires 'is_supply' and 'who_made'.
val featuredRank : kotlin.Int = 56 // kotlin.Int | The positive non-zero numeric position in the featured listings of the shop, with rank 1 listings appearing in the left-most position in featured listing on a shop's home page.
val isPersonalizable : kotlin.Boolean = true // kotlin.Boolean | When true, this listing is personalizable. The default value is null.
val personalizationIsRequired : kotlin.Boolean = true // kotlin.Boolean | When true, this listing requires personalization. The default value is null. Will only change if is_personalizable is 'true'.
val personalizationCharCountMax : kotlin.Int = 56 // kotlin.Int | This is an integer value representing the maximum length for the personalization message entered by the buyer. Will only change if is_personalizable is 'true'.
val personalizationInstructions : kotlin.String = personalizationInstructions_example // kotlin.String | A string representing instructions for the buyer to enter the personalization. Will only change if is_personalizable is 'true'.
val state : kotlin.String = state_example // kotlin.String | When _updating_ a listing, this value can be either `active` or `inactive`. Note: Setting a `draft` listing to `active` will also publish the listing on etsy.com and requires that the listing have an image set. Setting a `sold_out` listing to active will update the quantity to 1 and renew the listing on etsy.com.
val isSupply : kotlin.Boolean = true // kotlin.Boolean | When true, tags the listing as a supply product, else indicates that it's a finished product. Helps buyers locate the listing under the Supplies heading. Requires 'who_made' and 'when_made'.
val productionPartnerIds : kotlin.collections.List<kotlin.Long> =  // kotlin.collections.List<kotlin.Long> | An array of unique IDs of production partner ids.
val type : kotlin.String = type_example // kotlin.String | An enumerated type string that indicates whether the listing is physical or a digital download.
try {
    val result : ShopListing = apiInstance.updateListing(shopId, listingId, legacy, imageIds, title, description, materials, shouldAutoRenew, shippingProfileId, returnPolicyId, shopSectionId, itemWeight, itemLength, itemWidth, itemHeight, itemWeightUnit, itemDimensionsUnit, isTaxable, taxonomyId, tags, whoMade, whenMade, featuredRank, isPersonalizable, personalizationIsRequired, personalizationCharCountMax, personalizationInstructions, state, isSupply, productionPartnerIds, type)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#updateListing")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#updateListing")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |
| **imageIds** | [**kotlin.collections.List&lt;kotlin.Long&gt;**](kotlin.Long.md)| An array of numeric image IDs of the images in a listing, which can include up to 10 images. | [optional] |
| **title** | **kotlin.String**| The listing&#39;s title string. When creating or updating a listing, valid title strings contain only letters, numbers, punctuation marks, mathematical symbols, whitespace characters, ™, ©, and ®. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{P}\\\\p{Sm}\\\\p{Zs}™©®]/u) You can only use the %, :, &amp; and + characters once each. | [optional] |
| **description** | **kotlin.String**| A description string of the product for sale in the listing. | [optional] |
| **materials** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| A list of material strings for materials used in the product. Valid materials strings contain only letters, numbers, and whitespace characters. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}]/u) Default value is null. | [optional] |
| **shouldAutoRenew** | **kotlin.Boolean**| When true, renews a listing for four months upon expiration. | [optional] |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | [optional] |
| **returnPolicyId** | **kotlin.Long**| The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). Required for active physical listings. This requirement does not apply to listings of EU-based shops. | [optional] |
| **shopSectionId** | **kotlin.Int**| The numeric ID of the [shop section](/documentation/reference#tag/Shop-Section) for this listing. Default value is null. | [optional] |
| **itemWeight** | **kotlin.Float**| The numeric weight of the product measured in units set in &#39;item_weight_unit&#39;. Default value is null. If set, the value must be greater than 0. | [optional] |
| **itemLength** | **kotlin.Float**| The numeric length of the product measured in units set in &#39;item_dimensions_unit&#39;. Default value is null. If set, the value must be greater than 0. | [optional] |
| **itemWidth** | **kotlin.Float**| The numeric width of the product measured in units set in &#39;item_dimensions_unit&#39;. Default value is null. If set, the value must be greater than 0. | [optional] |
| **itemHeight** | **kotlin.Float**| The numeric height of the product measured in units set in &#39;item_dimensions_unit&#39;. Default value is null. If set, the value must be greater than 0. | [optional] |
| **itemWeightUnit** | **kotlin.String**| A string defining the units used to measure the weight of the product. Default value is null. | [optional] [enum: , oz, lb, g, kg] |
| **itemDimensionsUnit** | **kotlin.String**| A string defining the units used to measure the dimensions of the product. Default value is null. | [optional] [enum: , in, ft, mm, cm, m, yd, inches] |
| **isTaxable** | **kotlin.Boolean**| When true, applicable [shop](/documentation/reference#tag/Shop) tax rates apply to this listing at checkout. | [optional] |
| **taxonomyId** | **kotlin.Long**| The numerical taxonomy ID of the listing. See [SellerTaxonomy](/documentation/reference#tag/SellerTaxonomy) and [BuyerTaxonomy](/documentation/reference#tag/BuyerTaxonomy) for more information. | [optional] |
| **tags** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| A comma-separated list of tag strings for the listing. When creating or updating a listing, valid tag strings contain only letters, numbers, whitespace characters, -, &#39;, ™, ©, and ®. (regex: /[^\\\\p{L}\\\\p{Nd}\\\\p{Zs}\\\\-&#39;™©®]/u) Default value is null. | [optional] |
| **whoMade** | **kotlin.String**| An enumerated string indicating who made the product. Helps buyers locate the listing under the Handmade heading. Requires &#39;is_supply&#39; and &#39;when_made&#39;. | [optional] [enum: i_did, someone_else, collective] |
| **whenMade** | **kotlin.String**| An enumerated string for the era in which the maker made the product in this listing. Helps buyers locate the listing under the Vintage heading. Requires &#39;is_supply&#39; and &#39;who_made&#39;. | [optional] [enum: made_to_order, 2020_2025, 2010_2019, 2006_2009, before_2006, 2000_2005, 1990s, 1980s, 1970s, 1960s, 1950s, 1940s, 1930s, 1920s, 1910s, 1900s, 1800s, 1700s, before_1700] |
| **featuredRank** | **kotlin.Int**| The positive non-zero numeric position in the featured listings of the shop, with rank 1 listings appearing in the left-most position in featured listing on a shop&#39;s home page. | [optional] |
| **isPersonalizable** | **kotlin.Boolean**| When true, this listing is personalizable. The default value is null. | [optional] |
| **personalizationIsRequired** | **kotlin.Boolean**| When true, this listing requires personalization. The default value is null. Will only change if is_personalizable is &#39;true&#39;. | [optional] |
| **personalizationCharCountMax** | **kotlin.Int**| This is an integer value representing the maximum length for the personalization message entered by the buyer. Will only change if is_personalizable is &#39;true&#39;. | [optional] |
| **personalizationInstructions** | **kotlin.String**| A string representing instructions for the buyer to enter the personalization. Will only change if is_personalizable is &#39;true&#39;. | [optional] |
| **state** | **kotlin.String**| When _updating_ a listing, this value can be either &#x60;active&#x60; or &#x60;inactive&#x60;. Note: Setting a &#x60;draft&#x60; listing to &#x60;active&#x60; will also publish the listing on etsy.com and requires that the listing have an image set. Setting a &#x60;sold_out&#x60; listing to active will update the quantity to 1 and renew the listing on etsy.com. | [optional] [enum: active, inactive] |
| **isSupply** | **kotlin.Boolean**| When true, tags the listing as a supply product, else indicates that it&#39;s a finished product. Helps buyers locate the listing under the Supplies heading. Requires &#39;who_made&#39; and &#39;when_made&#39;. | [optional] |
| **productionPartnerIds** | [**kotlin.collections.List&lt;kotlin.Long&gt;**](kotlin.Long.md)| An array of unique IDs of production partner ids. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **type** | **kotlin.String**| An enumerated type string that indicates whether the listing is physical or a digital download. | [optional] [enum: physical, download, both] |

### Return type

[**ShopListing**](ShopListing.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="updateListingProperty"></a>
# **updateListingProperty**
> ListingPropertyValue updateListingProperty(shopId, listingId, propertyId, valueIds, values, scaleId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates or populates the properties list defining product offerings for a listing. Each offering requires both a &#x60;value&#x60; and a &#x60;value_id&#x60; that are valid for a &#x60;scale_id&#x60; assigned to the listing or that you assign to the listing with this request.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopListingApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val propertyId : kotlin.Long = 789 // kotlin.Long | The unique ID of an Etsy [listing property](/documentation/reference#operation/getListingProperties).
val valueIds : kotlin.collections.List<kotlin.Long> =  // kotlin.collections.List<kotlin.Long> | An array of unique IDs of multiple Etsy [listing property](/documentation/reference#operation/getListingProperties) values. For example, if your listing offers different sizes of a product, then the value ID list contains value IDs for each size.
val values : kotlin.collections.List<kotlin.String> =  // kotlin.collections.List<kotlin.String> | An array of value strings for multiple Etsy [listing property](/documentation/reference#operation/getListingProperties) values. For example, if your listing offers different colored products, then the values array contains the color strings for each color. Note: parenthesis characters (`(` and `)`) are not allowed.
val scaleId : kotlin.Long = 789 // kotlin.Long | The numeric ID of a single Etsy.com measurement scale. For example, for shoe size, there are three `scale_id`s available - `UK`, `US/Canada`, and `EU`, where `US/Canada` has `scale_id` 19.
try {
    val result : ListingPropertyValue = apiInstance.updateListingProperty(shopId, listingId, propertyId, valueIds, values, scaleId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopListingApi#updateListingProperty")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopListingApi#updateListingProperty")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **propertyId** | **kotlin.Long**| The unique ID of an Etsy [listing property](/documentation/reference#operation/getListingProperties). | |
| **valueIds** | [**kotlin.collections.List&lt;kotlin.Long&gt;**](kotlin.Long.md)| An array of unique IDs of multiple Etsy [listing property](/documentation/reference#operation/getListingProperties) values. For example, if your listing offers different sizes of a product, then the value ID list contains value IDs for each size. | |
| **values** | [**kotlin.collections.List&lt;kotlin.String&gt;**](kotlin.String.md)| An array of value strings for multiple Etsy [listing property](/documentation/reference#operation/getListingProperties) values. For example, if your listing offers different colored products, then the values array contains the color strings for each color. Note: parenthesis characters (&#x60;(&#x60; and &#x60;)&#x60;) are not allowed. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **scaleId** | **kotlin.Long**| The numeric ID of a single Etsy.com measurement scale. For example, for shoe size, there are three &#x60;scale_id&#x60;s available - &#x60;UK&#x60;, &#x60;US/Canada&#x60;, and &#x60;EU&#x60;, where &#x60;US/Canada&#x60; has &#x60;scale_id&#x60; 19. | [optional] |

### Return type

[**ListingPropertyValue**](ListingPropertyValue.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

