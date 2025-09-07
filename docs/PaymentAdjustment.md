
# PaymentAdjustment

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **paymentAdjustmentId** | **kotlin.Long** | The numeric ID for a payment adjustment. |  [optional] |
| **paymentId** | **kotlin.Long** | A unique numeric ID for a payment to a specific Etsy [shop](/documentation/reference#tag/Shop). |  [optional] |
| **status** | **kotlin.String** | The status string of the payment adjustment. |  [optional] |
| **isSuccess** | **kotlin.Boolean** | When true, the payment adjustment was or is likely to complete successfully. |  [optional] |
| **userId** | **kotlin.Long** | The numeric ID for the [user](/documentation/reference#tag/User) (seller) fulfilling the purchase. |  [optional] |
| **reasonCode** | **kotlin.String** | A human-readable string describing the reason for the refund. |  [optional] |
| **totalAdjustmentAmount** | **kotlin.Int** | The total numeric amount of the refund in the payment currency. |  [optional] |
| **shopTotalAdjustmentAmount** | **kotlin.Int** | The numeric amount of the refund in the shop currency. |  [optional] |
| **buyerTotalAdjustmentAmount** | **kotlin.Int** | The numeric amount of the refund in the buyer currency. |  [optional] |
| **totalFeeAdjustmentAmount** | **kotlin.Int** | The numeric amount of card processing fees associated with a payment adjustment. |  [optional] |
| **createTimestamp** | **kotlin.Int** | The transaction&#39;s creation date and time, in epoch seconds. |  [optional] |
| **createdTimestamp** | **kotlin.Int** | The transaction&#39;s creation date and time, in epoch seconds. |  [optional] |
| **updateTimestamp** | **kotlin.Int** | The date and time of the last change to the payment adjustment in epoch seconds. |  [optional] |
| **updatedTimestamp** | **kotlin.Int** | The date and time of the last change to the payment adjustment in epoch seconds. |  [optional] |
| **paymentAdjustmentItems** | [**kotlin.collections.List&lt;PaymentAdjustmentItem&gt;**](PaymentAdjustmentItem.md) | List of payment adjustment line items. |  [optional] |



