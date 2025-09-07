
# ShopReceipt

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **receiptId** | **kotlin.Long** | The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction. |  [optional] |
| **receiptType** | **kotlin.Int** | The numeric value for the Etsy channel that serviced the purchase: 0 for Etsy.com, 1 for a Pattern shop. |  [optional] |
| **sellerUserId** | **kotlin.Long** | The numeric ID for the [user](/documentation/reference#tag/User) (seller) fulfilling the purchase. |  [optional] |
| **sellerEmail** | **kotlin.String** | The email address string for the seller of the listing. |  [optional] |
| **buyerUserId** | **kotlin.Long** | The numeric ID for the [user](/documentation/reference#tag/User) making the purchase. |  [optional] |
| **buyerEmail** | **kotlin.String** | The email address string for the buyer of the listing. It will be null if access hasn&#39;t been granted. Access is case-by-case and subject to approval. |  [optional] |
| **name** | **kotlin.String** | The name string for the recipient in the shipping address. |  [optional] |
| **firstLine** | **kotlin.String** | The first address line string for the recipient in the shipping address. |  [optional] |
| **secondLine** | **kotlin.String** | The optional second address line string for the recipient in the shipping address. |  [optional] |
| **city** | **kotlin.String** | The city string for the recipient in the shipping address. |  [optional] |
| **state** | **kotlin.String** | The state string for the recipient in the shipping address. |  [optional] |
| **zip** | **kotlin.String** | The zip code string (not necessarily a number) for the recipient in the shipping address. |  [optional] |
| **status** | [**inline**](#Status) | The current order status string. One of: &#x60;paid&#x60;, &#x60;completed&#x60;, &#x60;open&#x60;, &#x60;payment processing&#x60; or &#x60;canceled&#x60;. |  [optional] |
| **formattedAddress** | **kotlin.String** | The formatted shipping address string for the recipient in the shipping address. |  [optional] |
| **countryIso** | **kotlin.String** | The ISO-3166 alpha-2 country code string for the recipient in the shipping address. |  [optional] |
| **paymentMethod** | **kotlin.String** | The payment method string identifying purchaser&#39;s payment method, which must be one of: &#39;cc&#39; (credit card), &#39;paypal&#39;, &#39;check&#39;, &#39;mo&#39; (money order), &#39;bt&#39; (bank transfer), &#39;other&#39;, &#39;ideal&#39;, &#39;sofort&#39;, &#39;apple_pay&#39;, &#39;google&#39;, &#39;android_pay&#39;, &#39;google_pay&#39;, &#39;klarna&#39;, &#39;k_pay_in_4&#39; (klarna), &#39;k_pay_in_3&#39; (klarna), or &#39;k_financing&#39; (klarna). |  [optional] |
| **paymentEmail** | **kotlin.String** | The email address string for the email address to which to send payment confirmation |  [optional] |
| **messageFromSeller** | **kotlin.String** | An optional message string from the seller. |  [optional] |
| **messageFromBuyer** | **kotlin.String** | An optional message string from the buyer. |  [optional] |
| **messageFromPayment** | **kotlin.String** | The machine-generated acknowledgement string from the payment system. |  [optional] |
| **isPaid** | **kotlin.Boolean** | When true, buyer paid for this purchase. |  [optional] |
| **isShipped** | **kotlin.Boolean** | When true, seller shipped the products. |  [optional] |
| **createTimestamp** | **kotlin.Int** | The receipt&#39;s creation time, in epoch seconds. |  [optional] |
| **createdTimestamp** | **kotlin.Int** | The receipt&#39;s creation time, in epoch seconds. |  [optional] |
| **updateTimestamp** | **kotlin.Int** | The time of the last update to the receipt, in epoch seconds. |  [optional] |
| **updatedTimestamp** | **kotlin.Int** | The time of the last update to the receipt, in epoch seconds. |  [optional] |
| **isGift** | **kotlin.Boolean** | When true, the buyer indicated this purchase is a gift. |  [optional] |
| **giftMessage** | **kotlin.String** | A gift message string the buyer requests delivered with the product. |  [optional] |
| **giftSender** | **kotlin.String** | The name of the person who sent the gift. |  [optional] |
| **grandtotal** | [**Money**](Money.md) | A number equal to the total_price minus the coupon discount plus tax and shipping costs. |  [optional] |
| **subtotal** | [**Money**](Money.md) | A number equal to the total_price minus coupon discounts. Does not included tax or shipping costs. |  [optional] |
| **totalPrice** | [**Money**](Money.md) | A number equal to the sum of the individual listings&#39; (price * quantity). Does not included tax or shipping costs. |  [optional] |
| **totalShippingCost** | [**Money**](Money.md) | A number equal to the total shipping cost of the receipt. |  [optional] |
| **totalTaxCost** | [**Money**](Money.md) | The total sales tax of the receipt. |  [optional] |
| **totalVatCost** | [**Money**](Money.md) | A number equal to the total value-added tax (VAT) of the receipt. |  [optional] |
| **discountAmt** | [**Money**](Money.md) | The numeric total discounted price for the receipt when using a discount (percent or fixed) coupon. Free shipping coupons are not included in this discount amount. |  [optional] |
| **giftWrapPrice** | [**Money**](Money.md) | The numeric price of gift wrap for this receipt. |  [optional] |
| **shipments** | [**kotlin.collections.List&lt;ShopReceiptShipment&gt;**](ShopReceiptShipment.md) | A list of shipment statements for this receipt. |  [optional] |
| **transactions** | [**kotlin.collections.List&lt;ShopReceiptTransaction&gt;**](ShopReceiptTransaction.md) | Array of transactions for the receipt. |  [optional] |
| **refunds** | [**kotlin.collections.List&lt;ShopRefund&gt;**](ShopRefund.md) | Refunds for a given receipt. |  [optional] |


<a id="Status"></a>
## Enum: status
| Name | Value |
| ---- | ----- |
| status | paid, completed, open, payment processing, canceled, fully refunded, partially refunded |



