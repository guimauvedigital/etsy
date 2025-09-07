# ShopApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**findShops**](ShopApi.md#findShops) | **GET** /v3/application/shops |  |
| [**getShop**](ShopApi.md#getShop) | **GET** /v3/application/shops/{shop_id} |  |
| [**getShopByOwnerUserId**](ShopApi.md#getShopByOwnerUserId) | **GET** /v3/application/users/{user_id}/shops |  |
| [**updateShop**](ShopApi.md#updateShop) | **PUT** /v3/application/shops/{shop_id} |  |


<a id="findShops"></a>
# **findShops**
> Shops findShops(shopName, limit, offset)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 endpoint for searching shops by name. Note: We make every effort to ensure that frozen or removed shops are not included in the search results. However, rarely, due to timing issues, they may appear.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopApi()
val shopName : kotlin.String = shopName_example // kotlin.String | The shop's name string.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
try {
    val result : Shops = apiInstance.findShops(shopName, limit, offset)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopApi#findShops")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopApi#findShops")
    e.printStackTrace()
}
```

### Parameters
| **shopName** | **kotlin.String**| The shop&#39;s name string. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |

### Return type

[**Shops**](Shops.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShop"></a>
# **getShop**
> Shop getShop(shopId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves the shop identified by a specific shop ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
try {
    val result : Shop = apiInstance.getShop(shopId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopApi#getShop")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopApi#getShop")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |

### Return type

[**Shop**](Shop.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopByOwnerUserId"></a>
# **getShopByOwnerUserId**
> Shop getShopByOwnerUserId(userId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves the shop identified by the shop owner&#39;s user ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopApi()
val userId : kotlin.Long = 789 // kotlin.Long | The numeric user ID of the [user](/documentation/reference#tag/User) who owns this shop.
try {
    val result : Shop = apiInstance.getShopByOwnerUserId(userId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopApi#getShopByOwnerUserId")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopApi#getShopByOwnerUserId")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **userId** | **kotlin.Long**| The numeric user ID of the [user](/documentation/reference#tag/User) who owns this shop. | |

### Return type

[**Shop**](Shop.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateShop"></a>
# **updateShop**
> Shop updateShop(shopId, title, announcement, saleMessage, digitalSaleMessage, policyAdditional)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates a shop. Assumes that all string parameters are provided in the shop&#39;s primary language. Please note that the policy_additional field should only be set for shops located in the EU. Passing a value for this field for shops outside of the EU, will result in an error.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val title : kotlin.String = title_example // kotlin.String | A brief heading string for the shop's main page.
val announcement : kotlin.String = announcement_example // kotlin.String | An announcement string to buyers that displays on the shop's homepage.
val saleMessage : kotlin.String = saleMessage_example // kotlin.String | A message string sent to users who complete a purchase from this shop.
val digitalSaleMessage : kotlin.String = digitalSaleMessage_example // kotlin.String | A message string sent to users who purchase a digital item from this shop.
val policyAdditional : kotlin.String = policyAdditional_example // kotlin.String | The shop's additional policies string (may be blank).
try {
    val result : Shop = apiInstance.updateShop(shopId, title, announcement, saleMessage, digitalSaleMessage, policyAdditional)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopApi#updateShop")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopApi#updateShop")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **title** | **kotlin.String**| A brief heading string for the shop&#39;s main page. | [optional] |
| **announcement** | **kotlin.String**| An announcement string to buyers that displays on the shop&#39;s homepage. | [optional] |
| **saleMessage** | **kotlin.String**| A message string sent to users who complete a purchase from this shop. | [optional] |
| **digitalSaleMessage** | **kotlin.String**| A message string sent to users who purchase a digital item from this shop. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **policyAdditional** | **kotlin.String**| The shop&#39;s additional policies string (may be blank). | [optional] |

### Return type

[**Shop**](Shop.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

