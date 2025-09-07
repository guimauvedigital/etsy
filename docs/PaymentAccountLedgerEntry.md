
# PaymentAccountLedgerEntry

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **entryId** | **kotlin.Long** | The ledger entry&#39;s numeric ID. |  [optional] |
| **ledgerId** | **kotlin.Long** | The ledger&#39;s numeric ID. |  [optional] |
| **sequenceNumber** | **kotlin.Int** | The sequence allows ledger entries to be sorted chronologically. The higher the sequence, the more recent the entry. |  [optional] |
| **amount** | **kotlin.Int** | The amount of money credited to the ledger. |  [optional] |
| **currency** | **kotlin.String** | The currency of the entry on the ledger. |  [optional] |
| **description** | **kotlin.String** | Details what kind of ledger entry this is: a payment, refund, reversal of a failed refund, disbursement, returned disbursement, recoupment, miscellaneous credit, miscellaneous debit, or bill payment. |  [optional] |
| **balance** | **kotlin.Int** | The amount of money in the shop&#39;s ledger the moment after this entry was applied. |  [optional] |
| **createDate** | **kotlin.Int** | The date and time the ledger entry was created in Epoch seconds. |  [optional] |
| **createdTimestamp** | **kotlin.Int** | The date and time the ledger entry was created in Epoch seconds. |  [optional] |
| **ledgerType** | **kotlin.String** | The original reference type for the ledger entry. |  [optional] |
| **referenceType** | **kotlin.String** | The object type the ledger entry refers to. |  [optional] |
| **referenceId** | **kotlin.String** | The object id the ledger entry refers to. |  [optional] |
| **paymentAdjustments** | [**kotlin.collections.List&lt;PaymentAdjustment&gt;**](PaymentAdjustment.md) | List of refund objects on an Etsy Payments transaction. All monetary amounts are in USD pennies unless otherwise specified. |  [optional] |



