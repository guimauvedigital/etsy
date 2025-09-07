
# ShopReceiptTransaction

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **transactionId** | **kotlin.Long** | The unique numeric ID for a transaction. |  [optional] |
| **title** | **kotlin.String** | The title string of the [listing](/documentation/reference#tag/ShopListing) purchased in this transaction. |  [optional] |
| **description** | **kotlin.String** | The description string of the [listing](/documentation/reference#tag/ShopListing) purchased in this transaction. |  [optional] |
| **sellerUserId** | **kotlin.Long** | The numeric user ID for the seller in this transaction. |  [optional] |
| **buyerUserId** | **kotlin.Long** | The numeric user ID for the buyer in this transaction. |  [optional] |
| **createTimestamp** | **kotlin.Int** | The transaction&#39;s creation date and time, in epoch seconds. |  [optional] |
| **createdTimestamp** | **kotlin.Int** | The transaction&#39;s creation date and time, in epoch seconds. |  [optional] |
| **paidTimestamp** | **kotlin.Int** | The transaction&#39;s paid date and time, in epoch seconds. |  [optional] |
| **shippedTimestamp** | **kotlin.Int** | The transaction&#39;s shipping date and time, in epoch seconds. |  [optional] |
| **quantity** | **kotlin.Int** | The numeric quantity of products purchased in this transaction. |  [optional] |
| **listingImageId** | **kotlin.Long** | The numeric ID of the primary [listing image](/documentation/reference#tag/ShopListing-Image) for this transaction. |  [optional] |
| **receiptId** | **kotlin.Long** | The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction. |  [optional] |
| **isDigital** | **kotlin.Boolean** | When true, the transaction recorded the purchase of a digital listing. |  [optional] |
| **fileData** | **kotlin.String** | A string describing the files purchased in this transaction. |  [optional] |
| **listingId** | **kotlin.Int** | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. |  [optional] |
| **transactionType** | **kotlin.String** | The type string for the transaction, usually \&quot;listing\&quot;. |  [optional] |
| **productId** | **kotlin.Long** | The numeric ID for a specific [product](/documentation/reference#tag/ShopListing-Product) purchased from a listing. |  [optional] |
| **sku** | **kotlin.String** | The SKU string for the product |  [optional] |
| **price** | [**Money**](Money.md) | A money object representing the price recorded the transaction. |  [optional] |
| **shippingCost** | [**Money**](Money.md) | A money object representing the shipping cost for this transaction. |  [optional] |
| **variations** | [**kotlin.collections.List&lt;TransactionVariations&gt;**](TransactionVariations.md) | Array of variations and personalizations the buyer chose. |  [optional] |
| **productData** | [**kotlin.collections.List&lt;ListingPropertyValue&gt;**](ListingPropertyValue.md) | A list of property value entries for this product. Note: parenthesis characters (&#x60;(&#x60; and &#x60;)&#x60;) are not allowed. |  [optional] |
| **shippingProfileId** | **kotlin.Long** | The ID of the shipping profile selected for this listing. |  [optional] |
| **minProcessingDays** | **kotlin.Long** | The minimum number of days for processing the listing. |  [optional] |
| **maxProcessingDays** | **kotlin.Long** | The maximum number of days for processing the listing. |  [optional] |
| **shippingMethod** | **kotlin.String** | Name of the selected shipping method. |  [optional] |
| **shippingUpgrade** | **kotlin.String** | The name of the shipping upgrade selected for this listing. Default value is null. |  [optional] |
| **expectedShipDate** | **kotlin.Int** | The date &amp; time of the expected ship date, in epoch seconds. |  [optional] |
| **buyerCoupon** | **kotlin.Float** | The amount of the buyer coupon that was discounted in the shop&#39;s currency. |  [optional] |
| **shopCoupon** | **kotlin.Float** | The amount of the shop coupon that was discounted in the shop&#39;s currency. |  [optional] |



