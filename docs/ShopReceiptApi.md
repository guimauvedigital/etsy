# ShopReceiptApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createReceiptShipment**](ShopReceiptApi.md#createReceiptShipment) | **POST** /v3/application/shops/{shop_id}/receipts/{receipt_id}/tracking |  |
| [**getShopReceipt**](ShopReceiptApi.md#getShopReceipt) | **GET** /v3/application/shops/{shop_id}/receipts/{receipt_id} |  |
| [**getShopReceipts**](ShopReceiptApi.md#getShopReceipts) | **GET** /v3/application/shops/{shop_id}/receipts |  |
| [**updateShopReceipt**](ShopReceiptApi.md#updateShopReceipt) | **PUT** /v3/application/shops/{shop_id}/receipts/{receipt_id} |  |


<a id="createReceiptShipment"></a>
# **createReceiptShipment**
> ShopReceipt createReceiptShipment(shopId, receiptId, legacy, trackingCode, carrierName, sendBcc, noteToBuyer)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Submits tracking information for a Shop Receipt, which creates a Shop Receipt Shipment entry for the given receipt_id. Each time you successfully submit tracking info, Etsy sends a notification email to the buyer User. When send_bcc is true, Etsy sends shipping notifications to the seller as well. When tracking_code and carrier_name aren&#39;t sent, the receipt is marked as shipped only. If the carrier is not supported, you may use &#x60;other&#x60; as the carrier name so you can provide the tracking code. **NOTES** When shipping within the United States AND the order is over $10 _or_ when shipping to India, tracking code and carrier name ARE required. Access to ShopReceipt&#39;s first_line, second_line, city, state, zip, country_iso and formatted_address is contingent in some regions to a preferred partnership status with Etsy

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReceiptApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val receiptId : kotlin.Long = 789 // kotlin.Long | The receipt to submit tracking for.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
val trackingCode : kotlin.String = trackingCode_example // kotlin.String | The tracking code for this receipt.
val carrierName : kotlin.String = carrierName_example // kotlin.String | The carrier name for this receipt.
val sendBcc : kotlin.Boolean = true // kotlin.Boolean | If true, the shipping notification will be sent to the seller as well
val noteToBuyer : kotlin.String = noteToBuyer_example // kotlin.String | Message to include in notification to the buyer.
try {
    val result : ShopReceipt = apiInstance.createReceiptShipment(shopId, receiptId, legacy, trackingCode, carrierName, sendBcc, noteToBuyer)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReceiptApi#createReceiptShipment")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReceiptApi#createReceiptShipment")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **receiptId** | **kotlin.Long**| The receipt to submit tracking for. | |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |
| **trackingCode** | **kotlin.String**| The tracking code for this receipt. | [optional] |
| **carrierName** | **kotlin.String**| The carrier name for this receipt. | [optional] |
| **sendBcc** | **kotlin.Boolean**| If true, the shipping notification will be sent to the seller as well | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **noteToBuyer** | **kotlin.String**| Message to include in notification to the buyer. | [optional] |

### Return type

[**ShopReceipt**](ShopReceipt.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="getShopReceipt"></a>
# **getShopReceipt**
> ShopReceipt getShopReceipt(shopId, receiptId, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a receipt, identified by a receipt id, from an Etsy shop. **NOTE** Access to ShopReceipt&#39;s first_line, second_line, city, state, zip, country_iso and formatted_address is contingent in some regions to a preferred partnership status with Etsy

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReceiptApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val receiptId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ShopReceipt = apiInstance.getShopReceipt(shopId, receiptId, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReceiptApi#getShopReceipt")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReceiptApi#getShopReceipt")
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

[**ShopReceipt**](ShopReceipt.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopReceipts"></a>
# **getShopReceipts**
> ShopReceipts getShopReceipts(shopId, minCreated, maxCreated, minLastModified, maxLastModified, limit, offset, sortOn, sortOrder, wasPaid, wasShipped, wasDelivered, wasCanceled, legacy)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Requests the Shop Receipts from a specific Shop, unfiltered or filtered by receipt id range or offset, date, paid, and/or shipped purchases. **NOTE** Access to ShopReceipt&#39;s first_line, second_line, city, state, zip, country_iso and formatted_address is contingent in some regions to a preferred partnership status with Etsy

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReceiptApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val minCreated : kotlin.Int = 56 // kotlin.Int | The earliest unix timestamp for when a record was created.
val maxCreated : kotlin.Int = 56 // kotlin.Int | The latest unix timestamp for when a record was created.
val minLastModified : kotlin.Int = 56 // kotlin.Int | The earliest unix timestamp for when a record last changed.
val maxLastModified : kotlin.Int = 56 // kotlin.Int | The latest unix timestamp for when a record last changed.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
val sortOn : kotlin.String = sortOn_example // kotlin.String | The value to sort a search result of listings on.
val sortOrder : kotlin.String = sortOrder_example // kotlin.String | The ascending(up) or descending(down) order to sort receipts by.
val wasPaid : kotlin.Boolean = true // kotlin.Boolean | When `true`, returns receipts where the seller has recieved payment for the receipt. When `false`, returns receipts where payment has not been received.
val wasShipped : kotlin.Boolean = true // kotlin.Boolean | When `true`, returns receipts where the seller shipped the product(s) in this receipt. When `false`, returns receipts where shipment has not been set.
val wasDelivered : kotlin.Boolean = true // kotlin.Boolean | When `true`, returns receipts that have been marked as delivered. When `false`, returns receipts where shipment has not been marked as delivered.
val wasCanceled : kotlin.Boolean = true // kotlin.Boolean | When `true`, the endpoint will only return the canceled receipts. When `false`, the endpoint will only return non-canceled receipts.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
try {
    val result : ShopReceipts = apiInstance.getShopReceipts(shopId, minCreated, maxCreated, minLastModified, maxLastModified, limit, offset, sortOn, sortOrder, wasPaid, wasShipped, wasDelivered, wasCanceled, legacy)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReceiptApi#getShopReceipts")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReceiptApi#getShopReceipts")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **minCreated** | **kotlin.Int**| The earliest unix timestamp for when a record was created. | [optional] |
| **maxCreated** | **kotlin.Int**| The latest unix timestamp for when a record was created. | [optional] |
| **minLastModified** | **kotlin.Int**| The earliest unix timestamp for when a record last changed. | [optional] |
| **maxLastModified** | **kotlin.Int**| The latest unix timestamp for when a record last changed. | [optional] |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |
| **sortOn** | **kotlin.String**| The value to sort a search result of listings on. | [optional] [default to created] [enum: created, updated, receipt_id] |
| **sortOrder** | **kotlin.String**| The ascending(up) or descending(down) order to sort receipts by. | [optional] [default to desc] [enum: asc, ascending, desc, descending, up, down] |
| **wasPaid** | **kotlin.Boolean**| When &#x60;true&#x60;, returns receipts where the seller has recieved payment for the receipt. When &#x60;false&#x60;, returns receipts where payment has not been received. | [optional] |
| **wasShipped** | **kotlin.Boolean**| When &#x60;true&#x60;, returns receipts where the seller shipped the product(s) in this receipt. When &#x60;false&#x60;, returns receipts where shipment has not been set. | [optional] |
| **wasDelivered** | **kotlin.Boolean**| When &#x60;true&#x60;, returns receipts that have been marked as delivered. When &#x60;false&#x60;, returns receipts where shipment has not been marked as delivered. | [optional] |
| **wasCanceled** | **kotlin.Boolean**| When &#x60;true&#x60;, the endpoint will only return the canceled receipts. When &#x60;false&#x60;, the endpoint will only return non-canceled receipts. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |

### Return type

[**ShopReceipts**](ShopReceipts.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateShopReceipt"></a>
# **updateShopReceipt**
> ShopReceipt updateShopReceipt(shopId, receiptId, legacy, wasShipped, wasPaid)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates the status of a receipt, identified by a receipt id, from an Etsy shop. **NOTE** Access to ShopReceipt&#39;s first_line, second_line, city, state, zip, country_iso and formatted_address is contingent in some regions to a preferred partnership status with Etsy

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReceiptApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val receiptId : kotlin.Long = 789 // kotlin.Long | The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction.
val legacy : kotlin.Boolean = true // kotlin.Boolean | This parameter needed to enable new parameters and response values related to processing profiles.
val wasShipped : kotlin.Boolean = true // kotlin.Boolean | When `true`, returns receipts where the seller shipped the product(s) in this receipt. When `false`, returns receipts where shipment has not been set.
val wasPaid : kotlin.Boolean = true // kotlin.Boolean | When `true`, returns receipts where the seller has recieved payment for the receipt. When `false`, returns receipts where payment has not been received.
try {
    val result : ShopReceipt = apiInstance.updateShopReceipt(shopId, receiptId, legacy, wasShipped, wasPaid)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReceiptApi#updateShopReceipt")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReceiptApi#updateShopReceipt")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **receiptId** | **kotlin.Long**| The numeric ID for the [receipt](/documentation/reference#tag/Shop-Receipt) associated to this transaction. | |
| **legacy** | **kotlin.Boolean**| This parameter needed to enable new parameters and response values related to processing profiles. | [optional] |
| **wasShipped** | **kotlin.Boolean**| When &#x60;true&#x60;, returns receipts where the seller shipped the product(s) in this receipt. When &#x60;false&#x60;, returns receipts where shipment has not been set. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **wasPaid** | **kotlin.Boolean**| When &#x60;true&#x60;, returns receipts where the seller has recieved payment for the receipt. When &#x60;false&#x60;, returns receipts where payment has not been received. | [optional] |

### Return type

[**ShopReceipt**](ShopReceipt.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

