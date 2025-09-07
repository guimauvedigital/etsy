# PaymentApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getPaymentAccountLedgerEntryPayments**](PaymentApi.md#getPaymentAccountLedgerEntryPayments) | **GET** /v3/application/shops/{shop_id}/payment-account/ledger-entries/payments |  |
| [**getPayments**](PaymentApi.md#getPayments) | **GET** /v3/application/shops/{shop_id}/payments |  |
| [**getShopPaymentByReceiptId**](PaymentApi.md#getShopPaymentByReceiptId) | **GET** /v3/application/shops/{shop_id}/receipts/{receipt_id}/payments |  |


<a id="getPaymentAccountLedgerEntryPayments"></a>
# **getPaymentAccountLedgerEntryPayments**
> Payments getPaymentAccountLedgerEntryPayments(shopId, ledgerEntryIds)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Get a Payment from a PaymentAccount Ledger Entry ID, if applicable

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = PaymentApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val ledgerEntryIds : kotlin.collections.List<kotlin.Long> =  // kotlin.collections.List<kotlin.Long> | 
try {
    val result : Payments = apiInstance.getPaymentAccountLedgerEntryPayments(shopId, ledgerEntryIds)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PaymentApi#getPaymentAccountLedgerEntryPayments")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PaymentApi#getPaymentAccountLedgerEntryPayments")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ledgerEntryIds** | [**kotlin.collections.List&lt;kotlin.Long&gt;**](kotlin.Long.md)|  | |

### Return type

[**Payments**](Payments.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getPayments"></a>
# **getPayments**
> Payments getPayments(shopId, paymentIds)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a list of payments from a shop identified by &#x60;shop_id&#x60;. You can also filter results using a list of payment IDs.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = PaymentApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val paymentIds : kotlin.collections.List<kotlin.Long> =  // kotlin.collections.List<kotlin.Long> | A comma-separated array of Payment IDs numbers.
try {
    val result : Payments = apiInstance.getPayments(shopId, paymentIds)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PaymentApi#getPayments")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PaymentApi#getPayments")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **paymentIds** | [**kotlin.collections.List&lt;kotlin.Long&gt;**](kotlin.Long.md)| A comma-separated array of Payment IDs numbers. | |

### Return type

[**Payments**](Payments.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopPaymentByReceiptId"></a>
# **getShopPaymentByReceiptId**
> Payments getShopPaymentByReceiptId(shopId, receiptId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a payment from a specific receipt, identified by &#x60;receipt_id&#x60;, from a specific shop, identified by &#x60;shop_id&#x60;

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = PaymentApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val receiptId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction.
try {
    val result : Payments = apiInstance.getShopPaymentByReceiptId(shopId, receiptId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PaymentApi#getShopPaymentByReceiptId")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PaymentApi#getShopPaymentByReceiptId")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **receiptId** | **kotlin.Long**| The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction. | |

### Return type

[**Payments**](Payments.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

