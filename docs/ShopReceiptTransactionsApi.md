# ShopReceiptTransactionsApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getShopReceiptTransaction**](ShopReceiptTransactionsApi.md#getShopReceiptTransaction) | **GET** /v3/application/shops/{shop_id}/transactions/{transaction_id} |  |
| [**getShopReceiptTransactionsByListing**](ShopReceiptTransactionsApi.md#getShopReceiptTransactionsByListing) | **GET** /v3/application/shops/{shop_id}/listings/{listing_id}/transactions |  |
| [**getShopReceiptTransactionsByReceipt**](ShopReceiptTransactionsApi.md#getShopReceiptTransactionsByReceipt) | **GET** /v3/application/shops/{shop_id}/receipts/{receipt_id}/transactions |  |
| [**getShopReceiptTransactionsByShop**](ShopReceiptTransactionsApi.md#getShopReceiptTransactionsByShop) | **GET** /v3/application/shops/{shop_id}/transactions |  |


<a id="getShopReceiptTransaction"></a>
# **getShopReceiptTransaction**
> ShopReceiptTransaction getShopReceiptTransaction(shopId, transactionId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a transaction by transaction ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReceiptTransactionsApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val transactionId : kotlin.Long = 789 // kotlin.Long | The unique numeric ID for a transaction.
try {
    val result : ShopReceiptTransaction = apiInstance.getShopReceiptTransaction(shopId, transactionId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReceiptTransactionsApi#getShopReceiptTransaction")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReceiptTransactionsApi#getShopReceiptTransaction")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **transactionId** | **kotlin.Long**| The unique numeric ID for a transaction. | |

### Return type

[**ShopReceiptTransaction**](ShopReceiptTransaction.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopReceiptTransactionsByListing"></a>
# **getShopReceiptTransactionsByListing**
> ShopReceiptTransactions getShopReceiptTransactionsByListing(shopId, listingId, limit, offset, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves the list of transactions associated with a listing.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReceiptTransactionsApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val listingId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ShopReceiptTransactions = apiInstance.getShopReceiptTransactionsByListing(shopId, listingId, limit, offset, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReceiptTransactionsApi#getShopReceiptTransactionsByListing")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReceiptTransactionsApi#getShopReceiptTransactionsByListing")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **listingId** | **kotlin.Long**| The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ShopReceiptTransactions**](ShopReceiptTransactions.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopReceiptTransactionsByReceipt"></a>
# **getShopReceiptTransactionsByReceipt**
> ShopReceiptTransactions getShopReceiptTransactionsByReceipt(shopId, receiptId, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves the list of transactions associated with a specific receipt.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReceiptTransactionsApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val receiptId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ShopReceiptTransactions = apiInstance.getShopReceiptTransactionsByReceipt(shopId, receiptId, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReceiptTransactionsApi#getShopReceiptTransactionsByReceipt")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReceiptTransactionsApi#getShopReceiptTransactionsByReceipt")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **receiptId** | **kotlin.Long**| The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ShopReceiptTransactions**](ShopReceiptTransactions.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopReceiptTransactionsByShop"></a>
# **getShopReceiptTransactionsByShop**
> ShopReceiptTransactions getShopReceiptTransactionsByShop(shopId, limit, offset, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves the list of transactions associated with a shop.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReceiptTransactionsApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ShopReceiptTransactions = apiInstance.getShopReceiptTransactionsByShop(shopId, limit, offset, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReceiptTransactionsApi#getShopReceiptTransactionsByShop")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReceiptTransactionsApi#getShopReceiptTransactionsByShop")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ShopReceiptTransactions**](ShopReceiptTransactions.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

