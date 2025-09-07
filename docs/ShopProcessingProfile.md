
# ShopProcessingProfile

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long** | The unique positive non-zero numeric ID for an Etsy Shop. |  [optional] |
| **readinessStateId** | **kotlin.Long** | The numeric ID of the [processing profile](/documentation/reference#operation/getShopReadinessStateDefinition) associated with the listing. Required when listing type is &#x60;physical&#x60;. |  [optional] |
| **readinessState** | [**inline**](#ReadinessState) | The readiness state of a product: \\\&quot;1\\\&quot; means \\\&quot;ready_to_ship\\\&quot;, and \\\&quot;2\\\&quot; means \\\&quot;made_to_order\\\&quot; |  [optional] |
| **minProcessingDays** | **kotlin.Int** | The minimum number of days for processing a specific product. |  [optional] |
| **maxProcessingDays** | **kotlin.Int** | The maximum number of days for processing a specific product. |  [optional] |
| **processingDaysDisplayLabel** | **kotlin.String** | Translated display label string for processing days, for example \&quot;3 - 5 days\&quot;. |  [optional] |


<a id="ReadinessState"></a>
## Enum: readiness_state
| Name | Value |
| ---- | ----- |
| readinessState | ready_to_ship, made_to_order |



