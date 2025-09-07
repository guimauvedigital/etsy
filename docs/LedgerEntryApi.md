# LedgerEntryApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getShopPaymentAccountLedgerEntries**](LedgerEntryApi.md#getShopPaymentAccountLedgerEntries) | **GET** /v3/application/shops/{shop_id}/payment-account/ledger-entries |  |
| [**getShopPaymentAccountLedgerEntry**](LedgerEntryApi.md#getShopPaymentAccountLedgerEntry) | **GET** /v3/application/shops/{shop_id}/payment-account/ledger-entries/{ledger_entry_id} |  |


<a id="getShopPaymentAccountLedgerEntries"></a>
# **getShopPaymentAccountLedgerEntries**
> PaymentAccountLedgerEntries getShopPaymentAccountLedgerEntries(shopId, minCreated, maxCreated, limit, offset)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Get a Shop Payment Account Ledger&#39;s Entries

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = LedgerEntryApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val minCreated : kotlin.Int = 56 // kotlin.Int | The earliest unix timestamp for when a record was created.
val maxCreated : kotlin.Int = 56 // kotlin.Int | The latest unix timestamp for when a record was created.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
try {
    val result : PaymentAccountLedgerEntries = apiInstance.getShopPaymentAccountLedgerEntries(shopId, minCreated, maxCreated, limit, offset)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling LedgerEntryApi#getShopPaymentAccountLedgerEntries")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling LedgerEntryApi#getShopPaymentAccountLedgerEntries")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **minCreated** | **kotlin.Int**| The earliest unix timestamp for when a record was created. | |
| **maxCreated** | **kotlin.Int**| The latest unix timestamp for when a record was created. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |

### Return type

[**PaymentAccountLedgerEntries**](PaymentAccountLedgerEntries.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopPaymentAccountLedgerEntry"></a>
# **getShopPaymentAccountLedgerEntry**
> PaymentAccountLedgerEntry getShopPaymentAccountLedgerEntry(shopId, ledgerEntryId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Get a single Shop Payment Account Ledger&#39;s Entry

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = LedgerEntryApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val ledgerEntryId : kotlin.Long = 789 // kotlin.Long | The unique ID of the shop owner ledger entry.
try {
    val result : PaymentAccountLedgerEntry = apiInstance.getShopPaymentAccountLedgerEntry(shopId, ledgerEntryId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling LedgerEntryApi#getShopPaymentAccountLedgerEntry")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling LedgerEntryApi#getShopPaymentAccountLedgerEntry")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ledgerEntryId** | **kotlin.Long**| The unique ID of the shop owner ledger entry. | |

### Return type

[**PaymentAccountLedgerEntry**](PaymentAccountLedgerEntry.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

