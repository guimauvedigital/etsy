# UserAddressApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteUserAddress**](UserAddressApi.md#deleteUserAddress) | **DELETE** /v3/application/user/addresses/{user_address_id} |  |
| [**getUserAddress**](UserAddressApi.md#getUserAddress) | **GET** /v3/application/user/addresses/{user_address_id} |  |
| [**getUserAddresses**](UserAddressApi.md#getUserAddresses) | **GET** /v3/application/user/addresses |  |


<a id="deleteUserAddress"></a>
# **deleteUserAddress**
> deleteUserAddress(userAddressId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 endpoint to delete a UserAddress for a User.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = UserAddressApi()
val userAddressId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the user's address.
try {
    apiInstance.deleteUserAddress(userAddressId)
} catch (e: ClientException) {
    println("4xx response calling UserAddressApi#deleteUserAddress")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling UserAddressApi#deleteUserAddress")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **userAddressId** | **kotlin.Long**| The numeric ID of the user&#39;s address. | |

### Return type

null (empty response body)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getUserAddress"></a>
# **getUserAddress**
> UserAddress getUserAddress(userAddressId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 endpoint to retrieve a UserAddress for a User.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = UserAddressApi()
val userAddressId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the user's address.
try {
    val result : UserAddress = apiInstance.getUserAddress(userAddressId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling UserAddressApi#getUserAddress")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling UserAddressApi#getUserAddress")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **userAddressId** | **kotlin.Long**| The numeric ID of the user&#39;s address. | |

### Return type

[**UserAddress**](UserAddress.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getUserAddresses"></a>
# **getUserAddresses**
> UserAddresses getUserAddresses(limit, offset)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Open API V3 endpoint to retrieve UserAddresses for a User.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = UserAddressApi()
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
try {
    val result : UserAddresses = apiInstance.getUserAddresses(limit, offset)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling UserAddressApi#getUserAddresses")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling UserAddressApi#getUserAddresses")
    e.printStackTrace()
}
```

### Parameters
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |

### Return type

[**UserAddresses**](UserAddresses.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

