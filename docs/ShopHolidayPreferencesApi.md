# ShopHolidayPreferencesApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getHolidayPreferences**](ShopHolidayPreferencesApi.md#getHolidayPreferences) | **GET** /v3/application/shops/{shop_id}/holiday-preferences |  |
| [**updateHolidayPreferences**](ShopHolidayPreferencesApi.md#updateHolidayPreferences) | **PUT** /v3/application/shops/{shop_id}/holiday-preferences/{holiday_id} |  |


<a id="getHolidayPreferences"></a>
# **getHolidayPreferences**
> kotlin.collections.List&lt;ShopHolidayPreference&gt; getHolidayPreferences(shopId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a list of holidays that are available to a shop to set a preference for. Currently only supported in the US and CA

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopHolidayPreferencesApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
try {
    val result : kotlin.collections.List<ShopHolidayPreference> = apiInstance.getHolidayPreferences(shopId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopHolidayPreferencesApi#getHolidayPreferences")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopHolidayPreferencesApi#getHolidayPreferences")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |

### Return type

[**kotlin.collections.List&lt;ShopHolidayPreference&gt;**](ShopHolidayPreference.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateHolidayPreferences"></a>
# **updateHolidayPreferences**
> ShopHolidayPreference updateHolidayPreferences(shopId, holidayId, isWorking)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates the preference for whether the seller will process orders or not on the holiday. Currently only supported in the US and CA

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopHolidayPreferencesApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val holidayId : kotlin.String = holidayId_example // kotlin.String | The unique id that maps to the holiday a country observes. See the [Fulfillment Tutorial docs](https://developer.etsy.com/documentation/tutorials/fulfillment/#country-holidays) for more info
val isWorking : kotlin.Boolean = true // kotlin.Boolean | A boolean value for whether the shop will process orders on a particular holiday.
try {
    val result : ShopHolidayPreference = apiInstance.updateHolidayPreferences(shopId, holidayId, isWorking)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopHolidayPreferencesApi#updateHolidayPreferences")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopHolidayPreferencesApi#updateHolidayPreferences")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **holidayId** | **kotlin.String**| The unique id that maps to the holiday a country observes. See the [Fulfillment Tutorial docs](https://developer.etsy.com/documentation/tutorials/fulfillment/#country-holidays) for more info | [enum: 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **isWorking** | **kotlin.Boolean**| A boolean value for whether the shop will process orders on a particular holiday. | |

### Return type

[**ShopHolidayPreference**](ShopHolidayPreference.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

