
# ListingInventoryProduct

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **productId** | **kotlin.Long** | The numeric ID for a specific [product](/documentation/reference#tag/ShopListing-Product) purchased from a listing. |  [optional] |
| **sku** | **kotlin.String** | The SKU string for the product |  [optional] |
| **isDeleted** | **kotlin.Boolean** | When true, someone deleted this product. |  [optional] |
| **offerings** | [**kotlin.collections.List&lt;ListingInventoryProductOffering&gt;**](ListingInventoryProductOffering.md) | A list of product offering entries for this product. |  [optional] |
| **propertyValues** | [**kotlin.collections.List&lt;ListingPropertyValue&gt;**](ListingPropertyValue.md) | A list of property value entries for this product. Note: parenthesis characters (&#x60;(&#x60; and &#x60;)&#x60;) are not allowed. |  [optional] |



