# ShopReturnPolicyApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**consolidateShopReturnPolicies**](ShopReturnPolicyApi.md#consolidateShopReturnPolicies) | **POST** /v3/application/shops/{shop_id}/policies/return/consolidate |  |
| [**createShopReturnPolicy**](ShopReturnPolicyApi.md#createShopReturnPolicy) | **POST** /v3/application/shops/{shop_id}/policies/return |  |
| [**deleteShopReturnPolicy**](ShopReturnPolicyApi.md#deleteShopReturnPolicy) | **DELETE** /v3/application/shops/{shop_id}/policies/return/{return_policy_id} |  |
| [**getShopReturnPolicies**](ShopReturnPolicyApi.md#getShopReturnPolicies) | **GET** /v3/application/shops/{shop_id}/policies/return |  |
| [**getShopReturnPolicy**](ShopReturnPolicyApi.md#getShopReturnPolicy) | **GET** /v3/application/shops/{shop_id}/policies/return/{return_policy_id} |  |
| [**updateShopReturnPolicy**](ShopReturnPolicyApi.md#updateShopReturnPolicy) | **PUT** /v3/application/shops/{shop_id}/policies/return/{return_policy_id} |  |


<a id="consolidateShopReturnPolicies"></a>
# **consolidateShopReturnPolicies**
> ShopReturnPolicy consolidateShopReturnPolicies(shopId, sourceReturnPolicyId, destinationReturnPolicyId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Consolidates Return Policies by moving all listings from a source return policy to a destination return policy, and deleting the source return policy. This is commonly used in the event that a user attempts to update a Return Policy such that its data is a duplicate of some other Return Policy, which is prevented.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReturnPolicyApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val sourceReturnPolicyId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies).
val destinationReturnPolicyId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies).
try {
    val result : ShopReturnPolicy = apiInstance.consolidateShopReturnPolicies(shopId, sourceReturnPolicyId, destinationReturnPolicyId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReturnPolicyApi#consolidateShopReturnPolicies")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReturnPolicyApi#consolidateShopReturnPolicies")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **sourceReturnPolicyId** | **kotlin.Long**| The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **destinationReturnPolicyId** | **kotlin.Long**| The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). | |

### Return type

[**ShopReturnPolicy**](ShopReturnPolicy.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="createShopReturnPolicy"></a>
# **createShopReturnPolicy**
> ShopReturnPolicy createShopReturnPolicy(shopId, acceptsReturns, acceptsExchanges, returnDeadline)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Creates a new Return Policy. Note: if either accepts_returns or accepts_exchanges is true, then a return_deadline is required.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReturnPolicyApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val acceptsReturns : kotlin.Boolean = true // kotlin.Boolean | 
val acceptsExchanges : kotlin.Boolean = true // kotlin.Boolean | 
val returnDeadline : kotlin.Int = 56 // kotlin.Int | The deadline for the Return Policy, measured in days. The value must be one of the following: [7, 14, 21, 30, 45, 60, 90].
try {
    val result : ShopReturnPolicy = apiInstance.createShopReturnPolicy(shopId, acceptsReturns, acceptsExchanges, returnDeadline)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReturnPolicyApi#createShopReturnPolicy")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReturnPolicyApi#createShopReturnPolicy")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **acceptsReturns** | **kotlin.Boolean**|  | |
| **acceptsExchanges** | **kotlin.Boolean**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **returnDeadline** | **kotlin.Int**| The deadline for the Return Policy, measured in days. The value must be one of the following: [7, 14, 21, 30, 45, 60, 90]. | [optional] |

### Return type

[**ShopReturnPolicy**](ShopReturnPolicy.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="deleteShopReturnPolicy"></a>
# **deleteShopReturnPolicy**
> deleteShopReturnPolicy(shopId, returnPolicyId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Deletes an existing Return Policy. Deletion is only allowed for policies which have no associated listings – move them to another policy before attempting deletion.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReturnPolicyApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val returnPolicyId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies).
try {
    apiInstance.deleteShopReturnPolicy(shopId, returnPolicyId)
} catch (e: ClientException) {
    println("4xx response calling ShopReturnPolicyApi#deleteShopReturnPolicy")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReturnPolicyApi#deleteShopReturnPolicy")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **returnPolicyId** | **kotlin.Long**| The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). | |

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

<a id="getShopReturnPolicies"></a>
# **getShopReturnPolicies**
> ShopReturnPolicies getShopReturnPolicies(shopId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Returns a shop&#39;s list of existing Return Policies

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReturnPolicyApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
try {
    val result : ShopReturnPolicies = apiInstance.getShopReturnPolicies(shopId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReturnPolicyApi#getShopReturnPolicies")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReturnPolicyApi#getShopReturnPolicies")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |

### Return type

[**ShopReturnPolicies**](ShopReturnPolicies.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopReturnPolicy"></a>
# **getShopReturnPolicy**
> ShopReturnPolicy getShopReturnPolicy(shopId, returnPolicyId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves an existing Return Policy.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReturnPolicyApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val returnPolicyId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies).
try {
    val result : ShopReturnPolicy = apiInstance.getShopReturnPolicy(shopId, returnPolicyId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReturnPolicyApi#getShopReturnPolicy")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReturnPolicyApi#getShopReturnPolicy")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **returnPolicyId** | **kotlin.Long**| The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). | |

### Return type

[**ShopReturnPolicy**](ShopReturnPolicy.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateShopReturnPolicy"></a>
# **updateShopReturnPolicy**
> ShopReturnPolicy updateShopReturnPolicy(shopId, returnPolicyId, acceptsReturns, acceptsExchanges, returnDeadline)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates an existing Return Policy. Note: if either accepts_returns or accepts_exchanges is true, then a return_deadline is required.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopReturnPolicyApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val returnPolicyId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies).
val acceptsReturns : kotlin.Boolean = true // kotlin.Boolean | 
val acceptsExchanges : kotlin.Boolean = true // kotlin.Boolean | 
val returnDeadline : kotlin.Int = 56 // kotlin.Int | The deadline for the Return Policy, measured in days. The value must be one of the following: [7, 14, 21, 30, 45, 60, 90].
try {
    val result : ShopReturnPolicy = apiInstance.updateShopReturnPolicy(shopId, returnPolicyId, acceptsReturns, acceptsExchanges, returnDeadline)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopReturnPolicyApi#updateShopReturnPolicy")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopReturnPolicyApi#updateShopReturnPolicy")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **returnPolicyId** | **kotlin.Long**| The numeric ID of the [Return Policy](/documentation/reference#operation/getShopReturnPolicies). | |
| **acceptsReturns** | **kotlin.Boolean**|  | |
| **acceptsExchanges** | **kotlin.Boolean**|  | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **returnDeadline** | **kotlin.Int**| The deadline for the Return Policy, measured in days. The value must be one of the following: [7, 14, 21, 30, 45, 60, 90]. | [optional] |

### Return type

[**ShopReturnPolicy**](ShopReturnPolicy.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

