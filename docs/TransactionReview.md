
# TransactionReview

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long** | The shop&#39;s numeric ID. |  [optional] |
| **listingId** | **kotlin.Long** | The ID of the ShopListing that the TransactionReview belongs to. |  [optional] |
| **transactionId** | **kotlin.Long** | The ID of the ShopReceipt Transaction that the TransactionReview belongs to. |  [optional] |
| **buyerUserId** | **kotlin.Long** | The numeric ID of the user who was the buyer in this transaction. Note: This field may be absent, depending on the buyer&#39;s privacy settings. |  [optional] |
| **rating** | **kotlin.Int** | Rating value on scale from 1 to 5 |  [optional] |
| **review** | **kotlin.String** | A message left by the author, explaining the feedback, if provided. |  [optional] |
| **language** | **kotlin.String** | The language of the TransactionReview |  [optional] |
| **imageUrlFullxfull** | **kotlin.String** | The url to a photo provided with the feedback, dimensions fullxfull. Note: This field may be absent, depending on the buyer&#39;s privacy settings. |  [optional] |
| **createTimestamp** | **kotlin.Int** | The date and time the TransactionReview was created in epoch seconds. |  [optional] |
| **createdTimestamp** | **kotlin.Int** | The date and time the TransactionReview was created in epoch seconds. |  [optional] |
| **updateTimestamp** | **kotlin.Int** | The date and time the TransactionReview was updated in epoch seconds. |  [optional] |
| **updatedTimestamp** | **kotlin.Int** | The date and time the TransactionReview was updated in epoch seconds. |  [optional] |



