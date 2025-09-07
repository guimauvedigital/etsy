
# Shop

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long** | The unique positive non-zero numeric ID for an Etsy Shop. |  [optional] |
| **userId** | **kotlin.Long** | The numeric user ID of the [user](/documentation/reference#tag/User) who owns this shop. |  [optional] |
| **shopName** | **kotlin.String** | The shop&#39;s name string. |  [optional] |
| **createDate** | **kotlin.Int** | The date and time this shop was created, in epoch seconds. |  [optional] |
| **createdTimestamp** | **kotlin.Int** | The date and time this shop was created, in epoch seconds. |  [optional] |
| **title** | **kotlin.String** | A brief heading string for the shop&#39;s main page. |  [optional] |
| **announcement** | **kotlin.String** | An announcement string to buyers that displays on the shop&#39;s homepage. |  [optional] |
| **currencyCode** | **kotlin.String** | The ISO (alphabetic) code for the shop&#39;s currency. The shop displays all prices in this currency by default. |  [optional] |
| **isVacation** | **kotlin.Boolean** | When true, this shop is not accepting purchases. |  [optional] |
| **vacationMessage** | **kotlin.String** | The shop&#39;s message string displayed when &#x60;is_vacation&#x60; is true. |  [optional] |
| **saleMessage** | **kotlin.String** | A message string sent to users who complete a purchase from this shop. |  [optional] |
| **digitalSaleMessage** | **kotlin.String** | A message string sent to users who purchase a digital item from this shop. |  [optional] |
| **updateDate** | **kotlin.Int** | The date and time of the last update to the shop, in epoch seconds. |  [optional] |
| **updatedTimestamp** | **kotlin.Int** | The date and time of the last update to the shop, in epoch seconds. |  [optional] |
| **listingActiveCount** | **kotlin.Int** | The number of active listings in the shop. |  [optional] |
| **digitalListingCount** | **kotlin.Int** | The number of digital listings in the shop. |  [optional] |
| **loginName** | **kotlin.String** | The shop owner&#39;s login name string. |  [optional] |
| **acceptsCustomRequests** | **kotlin.Boolean** | When true, the shop accepts customization requests. |  [optional] |
| **policyWelcome** | **kotlin.String** | The shop&#39;s policy welcome string (may be blank). |  [optional] |
| **policyPayment** | **kotlin.String** | The shop&#39;s payment policy string (may be blank). |  [optional] |
| **policyShipping** | **kotlin.String** | The shop&#39;s shipping policy string (may be blank). |  [optional] |
| **policyRefunds** | **kotlin.String** | The shop&#39;s refund policy string (may be blank). |  [optional] |
| **policyAdditional** | **kotlin.String** | The shop&#39;s additional policies string (may be blank). |  [optional] |
| **policySellerInfo** | **kotlin.String** | The shop&#39;s seller information string (may be blank). |  [optional] |
| **policyUpdateDate** | **kotlin.Int** | The date and time of the last update to the shop&#39;s policies, in epoch seconds. |  [optional] |
| **policyHasPrivateReceiptInfo** | **kotlin.Boolean** | When true, EU receipts display private info. |  [optional] |
| **hasUnstructuredPolicies** | **kotlin.Boolean** | When true, the shop displays additional unstructured policy fields. |  [optional] |
| **policyPrivacy** | **kotlin.String** | The shop&#39;s privacy policy string (may be blank). |  [optional] |
| **vacationAutoreply** | **kotlin.String** | The shop&#39;s automatic reply string displayed in new conversations when &#x60;is_vacation&#x60; is true. |  [optional] |
| **url** | **kotlin.String** | The URL string for this shop. |  [optional] |
| **imageUrl760x100** | **kotlin.String** | The URL string for this shop&#39;s banner image. |  [optional] |
| **numFavorers** | **kotlin.Int** | The number of users who marked this shop a favorite. |  [optional] |
| **languages** | **kotlin.collections.List&lt;kotlin.String&gt;** | A list of language strings for the shop&#39;s enrolled languages where the default shop language is the first element in the array. |  [optional] |
| **iconUrlFullxfull** | **kotlin.String** | The URL string for this shop&#39;s icon image. |  [optional] |
| **isUsingStructuredPolicies** | **kotlin.Boolean** | When true, the shop accepted using structured policies. |  [optional] |
| **hasOnboardedStructuredPolicies** | **kotlin.Boolean** | When true, the shop accepted OR declined after viewing structured policies onboarding. |  [optional] |
| **includeDisputeFormLink** | **kotlin.Boolean** | When true, this shop&#39;s policies include a link to an EU online dispute form. |  [optional] |
| **isDirectCheckoutOnboarded** | **kotlin.Boolean** | (**DEPRECATED: Replaced by _is_etsy_payments_onboarded_.) When true, the shop has onboarded onto Etsy Payments. |  [optional] |
| **isEtsyPaymentsOnboarded** | **kotlin.Boolean** | When true, the shop has onboarded onto Etsy Payments. |  [optional] |
| **isCalculatedEligible** | **kotlin.Boolean** | When true, the shop is eligible for calculated shipping profiles. (Only available in the US and Canada) |  [optional] |
| **isOptedInToBuyerPromise** | **kotlin.Boolean** | When true, the shop opted in to buyer promise. |  [optional] |
| **isShopUsBased** | **kotlin.Boolean** | When true, the shop is based in the US. |  [optional] |
| **transactionSoldCount** | **kotlin.Int** | The total number of sales ([transactions](/documentation/reference#tag/Shop-Receipt-Transactions)) for this shop. |  [optional] |
| **shippingFromCountryIso** | **kotlin.String** | The country iso the shop is shipping from. |  [optional] |
| **shopLocationCountryIso** | **kotlin.String** | The country iso where the shop is located. |  [optional] |
| **reviewCount** | **kotlin.Int** | Number of reviews of shop listings in the past year. |  [optional] |
| **reviewAverage** | **kotlin.Float** | Average rating based on reviews of shop listings in the past year. |  [optional] |



