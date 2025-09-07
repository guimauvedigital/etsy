
# UpdateListingInventoryRequest

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **products** | [**kotlin.collections.List&lt;UpdateListingInventoryRequestProductsInner&gt;**](UpdateListingInventoryRequestProductsInner.md) | A JSON array of products available in a listing, even if only one product. All field names in the JSON blobs are lowercase. |  |
| **priceOnProperty** | **kotlin.collections.List&lt;kotlin.Int&gt;** | An array of unique [listing property](/documentation/reference#operation/getListingProperties) ID integers for the properties that change product prices, if any. For example, if you charge specific prices for different sized products in the same listing, then this array contains the property ID for size. |  [optional] |
| **quantityOnProperty** | **kotlin.collections.List&lt;kotlin.Int&gt;** | An array of unique [listing property](/documentation/reference#operation/getListingProperties) ID integers for the properties that change the quantity of the products, if any. For example, if you stock specific quantities of different colored products in the same listing, then this array contains the property ID for color. |  [optional] |
| **skuOnProperty** | **kotlin.collections.List&lt;kotlin.Int&gt;** | An array of unique [listing property](/documentation/reference#operation/getListingProperties) ID integers for the properties that change the product SKU, if any. For example, if you use specific skus for different colored products in the same listing, then this array contains the property ID for color. |  [optional] |
| **readinessStateOnProperty** | **kotlin.collections.List&lt;kotlin.Long&gt;** | An array of unique [listing property](/documentation/reference#operation/getListingProperties) ID integers for the properties that change processing profile, if any. For example, if you need specific processing profiles for different colored products in the same listing, then this array contains the property ID for color. |  [optional] |



