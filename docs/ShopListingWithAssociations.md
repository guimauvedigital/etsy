
# ShopListingWithAssociations

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **listingId** | **kotlin.Long** | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. |  [optional] |
| **userId** | **kotlin.Long** | The numeric ID for the [user](/documentation/reference#tag/User) posting the listing. |  [optional] |
| **shopId** | **kotlin.Long** | The unique positive non-zero numeric ID for an Etsy Shop. |  [optional] |
| **title** | **kotlin.String** | The listing&#39;s title string. When creating or updating a listing, valid title strings contain only letters, numbers, punctuation marks, mathematical symbols, whitespace characters, ™, ©, and ®. (regex: /[^\\p{L}\\p{Nd}\\p{P}\\p{Sm}\\p{Zs}™©®]/u) You can only use the %, :, &amp; and + characters once each. |  [optional] |
| **description** | **kotlin.String** | A description string of the product for sale in the listing. |  [optional] |
| **state** | [**inline**](#State) | When _updating_ a listing, this value can be either &#x60;active&#x60; or &#x60;inactive&#x60;. Note: Setting a &#x60;draft&#x60; listing to &#x60;active&#x60; will also publish the listing on etsy.com and requires that the listing have an image set. Setting a &#x60;sold_out&#x60; listing to active will update the quantity to 1 and renew the listing on etsy.com. |  [optional] |
| **creationTimestamp** | **kotlin.Int** | The listing&#39;s creation time, in epoch seconds. |  [optional] |
| **createdTimestamp** | **kotlin.Int** | The listing&#39;s creation time, in epoch seconds. |  [optional] |
| **endingTimestamp** | **kotlin.Int** | The listing&#39;s expiration time, in epoch seconds. |  [optional] |
| **originalCreationTimestamp** | **kotlin.Int** | The listing&#39;s creation time, in epoch seconds. |  [optional] |
| **lastModifiedTimestamp** | **kotlin.Int** | The time of the last update to the listing, in epoch seconds. |  [optional] |
| **updatedTimestamp** | **kotlin.Int** | The time of the last update to the listing, in epoch seconds. |  [optional] |
| **stateTimestamp** | **kotlin.Int** | The date and time of the last state change of this listing. |  [optional] |
| **quantity** | **kotlin.Int** | The positive non-zero number of products available for purchase in the listing. Note: The listing quantity is the sum of available offering quantities. You can request the quantities for individual offerings from the ListingInventory resource using the [getListingInventory](/documentation/reference#operation/getListingInventory) endpoint. |  [optional] |
| **shopSectionId** | **kotlin.Long** | The numeric ID of a section in a specific Etsy shop. |  [optional] |
| **featuredRank** | **kotlin.Int** | The positive non-zero numeric position in the featured listings of the shop, with rank 1 listings appearing in the left-most position in featured listing on a shop&#39;s home page. |  [optional] |
| **url** | **kotlin.String** | The full URL to the listing&#39;s page on Etsy. |  [optional] |
| **numFavorers** | **kotlin.Int** | The number of users who marked this Listing a favorite. |  [optional] |
| **nonTaxable** | **kotlin.Boolean** | When true, applicable [shop](/documentation/reference#tag/Shop) tax rates do not apply to this listing at checkout. |  [optional] |
| **isTaxable** | **kotlin.Boolean** | When true, applicable [shop](/documentation/reference#tag/Shop) tax rates apply to this listing at checkout. |  [optional] |
| **isCustomizable** | **kotlin.Boolean** | When true, a buyer may contact the seller for a customized order. The default value is true when a shop accepts custom orders. Does not apply to shops that do not accept custom orders. |  [optional] |
| **isPersonalizable** | **kotlin.Boolean** | When true, this listing is personalizable. The default value is null. |  [optional] |
| **personalizationIsRequired** | **kotlin.Boolean** | When true, this listing requires personalization. The default value is null. Will only change if is_personalizable is &#39;true&#39;. |  [optional] |
| **personalizationCharCountMax** | **kotlin.Int** | This is an integer value representing the maximum length for the personalization message entered by the buyer. Will only change if is_personalizable is &#39;true&#39;. |  [optional] |
| **personalizationInstructions** | **kotlin.String** | When true, this listing requires personalization. The default value is null. Will only change if is_personalizable is &#39;true&#39;. |  [optional] |
| **listingType** | [**inline**](#ListingType) | An enumerated type string that indicates whether the listing is physical or a digital download. |  [optional] |
| **tags** | **kotlin.collections.List&lt;kotlin.String&gt;** | A comma-separated list of tag strings for the listing. When creating or updating a listing, valid tag strings contain only letters, numbers, whitespace characters, -, &#39;, ™, ©, and ®. (regex: /[^\\p{L}\\p{Nd}\\p{Zs}\\-&#39;™©®]/u) Default value is null. |  [optional] |
| **materials** | **kotlin.collections.List&lt;kotlin.String&gt;** | A list of material strings for materials used in the product. Valid materials strings contain only letters, numbers, and whitespace characters. (regex: /[^\\p{L}\\p{Nd}\\p{Zs}]/u) Default value is null. |  [optional] |
| **shippingProfileId** | **kotlin.Long** | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. |  [optional] |
| **returnPolicyId** | **kotlin.Long** | The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). |  [optional] |
| **processingMin** | **kotlin.Int** | The minimum number of days required to process this listing. Default value is null. |  [optional] |
| **processingMax** | **kotlin.Int** | The maximum number of days required to process this listing. Default value is null. |  [optional] |
| **whoMade** | [**inline**](#WhoMade) | An enumerated string indicating who made the product. Helps buyers locate the listing under the Handmade heading. Requires &#39;is_supply&#39; and &#39;when_made&#39;. |  [optional] |
| **whenMade** | [**inline**](#WhenMade) | An enumerated string for the era in which the maker made the product in this listing. Helps buyers locate the listing under the Vintage heading. Requires &#39;is_supply&#39; and &#39;who_made&#39;. |  [optional] |
| **isSupply** | **kotlin.Boolean** | When true, tags the listing as a supply product, else indicates that it&#39;s a finished product. Helps buyers locate the listing under the Supplies heading. Requires &#39;who_made&#39; and &#39;when_made&#39;. |  [optional] |
| **itemWeight** | **kotlin.Float** | The numeric weight of the product measured in units set in &#39;item_weight_unit&#39;. Default value is null. If set, the value must be greater than 0. |  [optional] |
| **itemWeightUnit** | [**inline**](#ItemWeightUnit) | A string defining the units used to measure the weight of the product. Default value is null. |  [optional] |
| **itemLength** | **kotlin.Float** | The numeric length of the product measured in units set in &#39;item_dimensions_unit&#39;. Default value is null. If set, the value must be greater than 0. |  [optional] |
| **itemWidth** | **kotlin.Float** | The numeric width of the product measured in units set in &#39;item_dimensions_unit&#39;. Default value is null. If set, the value must be greater than 0. |  [optional] |
| **itemHeight** | **kotlin.Float** | The numeric length of the product measured in units set in &#39;item_dimensions_unit&#39;. Default value is null. If set, the value must be greater than 0. |  [optional] |
| **itemDimensionsUnit** | [**inline**](#ItemDimensionsUnit) | A string defining the units used to measure the dimensions of the product. Default value is null. |  [optional] |
| **isPrivate** | **kotlin.Boolean** | When true, this is a private listing intended for a specific buyer and hidden from shop view. |  [optional] |
| **style** | **kotlin.collections.List&lt;kotlin.String&gt;** | An array of style strings for this listing, each of which is free-form text string such as \&quot;Formal\&quot;, or \&quot;Steampunk\&quot;. When creating or updating a listing, the listing may have up to two styles. Valid style strings contain only letters, numbers, and whitespace characters. (regex: /[^\\p{L}\\p{Nd}\\p{Zs}]/u) Default value is null. |  [optional] |
| **fileData** | **kotlin.String** | A string describing the files attached to a digital listing. |  [optional] |
| **hasVariations** | **kotlin.Boolean** | When true, the listing has variations. |  [optional] |
| **shouldAutoRenew** | **kotlin.Boolean** | When true, renews a listing for four months upon expiration. |  [optional] |
| **language** | **kotlin.String** | The IETF language tag for the default language of the listing. Ex: &#x60;de&#x60;, &#x60;en&#x60;, &#x60;es&#x60;, &#x60;fr&#x60;, &#x60;it&#x60;, &#x60;ja&#x60;, &#x60;nl&#x60;, &#x60;pl&#x60;, &#x60;pt&#x60;, &#x60;ru&#x60;. |  [optional] |
| **price** | [**Money**](Money.md) | The positive non-zero price of the product. (Sold product listings are private) Note: The price is the minimum possible price. The [&#x60;getListingInventory&#x60;](/documentation/reference/#operation/getListingInventory) method requests exact prices for available offerings. |  [optional] |
| **taxonomyId** | **kotlin.Int** | The numerical taxonomy ID of the listing. See [SellerTaxonomy](/documentation/reference#tag/SellerTaxonomy) and [BuyerTaxonomy](/documentation/reference#tag/BuyerTaxonomy) for more information. |  [optional] |
| **readinessStateId** | **kotlin.Long** | The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is &#x60;physical&#x60;. |  [optional] |
| **shippingProfile** | [**ShopShippingProfile**](ShopShippingProfile.md) | An array of data representing the shipping profile resource. |  [optional] |
| **user** | [**User**](User.md) | Represents a single user of the site |  [optional] |
| **shop** | [**Shop**](Shop.md) | A shop created by an Etsy user. |  [optional] |
| **images** | [**kotlin.collections.List&lt;ListingImage&gt;**](ListingImage.md) | Represents a list of listing image resources, each of which contains the reference URLs and metadata for an image |  [optional] |
| **videos** | [**kotlin.collections.List&lt;ListingVideo&gt;**](ListingVideo.md) | The single video associated with a listing. |  [optional] |
| **inventory** | [**ListingInventory**](ListingInventory.md) | An enumerated string that attaches a valid association. Default value is null. |  [optional] |
| **productionPartners** | [**kotlin.collections.List&lt;ShopProductionPartner&gt;**](ShopProductionPartner.md) | Represents a list of production partners for a shop. |  [optional] |
| **skus** | **kotlin.collections.List&lt;kotlin.String&gt;** | A list of SKU strings for the listing. SKUs will only appear if the requesting user owns the shop and a valid matching OAuth 2 token is provided. When requested without the token it will be an empty array. |  [optional] |
| **translations** | [**ListingTranslations**](ListingTranslations.md) | A map of translations for the listing. Default value is a map of all supported languages keyed to null. |  [optional] |
| **views** | **kotlin.Int** | The number of times the listing has been viewed. This value is tabulated once per day and **only for active listings**, so the value is not real-time. If &#x60;0&#x60;, the listing has either not been viewed, not yet tabulated, was not active during the last tabulation or there was an error fetching the value. If a value is expected, call &#x60;getListing&#x60; to confirm the value. |  [optional] |


<a id="State"></a>
## Enum: state
| Name | Value |
| ---- | ----- |
| state | active, inactive, sold_out, draft, expired |


<a id="ListingType"></a>
## Enum: listing_type
| Name | Value |
| ---- | ----- |
| listingType | physical, download, both |


<a id="WhoMade"></a>
## Enum: who_made
| Name | Value |
| ---- | ----- |
| whoMade | i_did, someone_else, collective |


<a id="WhenMade"></a>
## Enum: when_made
| Name | Value |
| ---- | ----- |
| whenMade | made_to_order, 2020_2025, 2010_2019, 2006_2009, before_2006, 2000_2005, 1990s, 1980s, 1970s, 1960s, 1950s, 1940s, 1930s, 1920s, 1910s, 1900s, 1800s, 1700s, before_1700 |


<a id="ItemWeightUnit"></a>
## Enum: item_weight_unit
| Name | Value |
| ---- | ----- |
| itemWeightUnit | oz, lb, g, kg |


<a id="ItemDimensionsUnit"></a>
## Enum: item_dimensions_unit
| Name | Value |
| ---- | ----- |
| itemDimensionsUnit | in, ft, mm, cm, m, yd, inches |



