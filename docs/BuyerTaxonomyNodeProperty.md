
# BuyerTaxonomyNodeProperty

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **propertyId** | **kotlin.Long** | The unique numeric ID of this product property. |  [optional] |
| **name** | **kotlin.String** | The name string for this taxonomy node. |  [optional] |
| **displayName** | **kotlin.String** | The human-readable product property name string. |  [optional] |
| **scales** | [**kotlin.collections.List&lt;BuyerTaxonomyPropertyScale&gt;**](BuyerTaxonomyPropertyScale.md) | A list of available scales. |  [optional] |
| **isRequired** | **kotlin.Boolean** | When true, listings assigned eligible taxonomy IDs require this property. |  [optional] |
| **supportsAttributes** | **kotlin.Boolean** | When true, you can use this property in listing attributes. |  [optional] |
| **supportsVariations** | **kotlin.Boolean** | When true, you can use this property in listing variations. |  [optional] |
| **isMultivalued** | **kotlin.Boolean** | When true, you can assign multiple property values to this property |  [optional] |
| **maxValuesAllowed** | **kotlin.Int** | When true, you can assign multiple property values to this property |  [optional] |
| **possibleValues** | [**kotlin.collections.List&lt;BuyerTaxonomyPropertyValue&gt;**](BuyerTaxonomyPropertyValue.md) | A list of supported property value strings for this property. |  [optional] |
| **selectedValues** | [**kotlin.collections.List&lt;BuyerTaxonomyPropertyValue&gt;**](BuyerTaxonomyPropertyValue.md) | A list of property value strings automatically and always selected for the given property. |  [optional] |



