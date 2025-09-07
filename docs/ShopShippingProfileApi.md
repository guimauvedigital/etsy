# ShopShippingProfileApi

All URIs are relative to *https://openapi.etsy.com*

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createShopShippingProfile**](ShopShippingProfileApi.md#createShopShippingProfile) | **POST** /v3/application/shops/{shop_id}/shipping-profiles |  |
| [**createShopShippingProfileDestination**](ShopShippingProfileApi.md#createShopShippingProfileDestination) | **POST** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id}/destinations |  |
| [**createShopShippingProfileUpgrade**](ShopShippingProfileApi.md#createShopShippingProfileUpgrade) | **POST** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id}/upgrades |  |
| [**deleteShopShippingProfile**](ShopShippingProfileApi.md#deleteShopShippingProfile) | **DELETE** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id} |  |
| [**deleteShopShippingProfileDestination**](ShopShippingProfileApi.md#deleteShopShippingProfileDestination) | **DELETE** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id}/destinations/{shipping_profile_destination_id} |  |
| [**deleteShopShippingProfileUpgrade**](ShopShippingProfileApi.md#deleteShopShippingProfileUpgrade) | **DELETE** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id}/upgrades/{upgrade_id} |  |
| [**getShippingCarriers**](ShopShippingProfileApi.md#getShippingCarriers) | **GET** /v3/application/shipping-carriers |  |
| [**getShopShippingProfile**](ShopShippingProfileApi.md#getShopShippingProfile) | **GET** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id} |  |
| [**getShopShippingProfileDestinationsByShippingProfile**](ShopShippingProfileApi.md#getShopShippingProfileDestinationsByShippingProfile) | **GET** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id}/destinations |  |
| [**getShopShippingProfileUpgrades**](ShopShippingProfileApi.md#getShopShippingProfileUpgrades) | **GET** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id}/upgrades |  |
| [**getShopShippingProfiles**](ShopShippingProfileApi.md#getShopShippingProfiles) | **GET** /v3/application/shops/{shop_id}/shipping-profiles |  |
| [**updateShopShippingProfile**](ShopShippingProfileApi.md#updateShopShippingProfile) | **PUT** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id} |  |
| [**updateShopShippingProfileDestination**](ShopShippingProfileApi.md#updateShopShippingProfileDestination) | **PUT** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id}/destinations/{shipping_profile_destination_id} |  |
| [**updateShopShippingProfileUpgrade**](ShopShippingProfileApi.md#updateShopShippingProfileUpgrade) | **PUT** /v3/application/shops/{shop_id}/shipping-profiles/{shipping_profile_id}/upgrades/{upgrade_id} |  |


<a id="createShopShippingProfile"></a>
# **createShopShippingProfile**
> ShopShippingProfile createShopShippingProfile(shopId, title, originCountryIso, primaryCost, secondaryCost, minProcessingTime, maxProcessingTime, processingTimeUnit, destinationCountryIso, destinationRegion, originPostalCode, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Creates a new ShippingProfile. You can pass a country iso code or a region when creating a ShippingProfile, but not both. Only one is required. You must pass either a shipping_carrier_id AND mail_class, or both min and max_delivery_days.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val title : kotlin.String = title_example // kotlin.String | The name string of this shipping profile.
val originCountryIso : kotlin.String = originCountryIso_example // kotlin.String | The ISO code of the country from which the listing ships.
val primaryCost : kotlin.Float = 3.4 // kotlin.Float | The cost of shipping to this country/region alone, measured in the store's default currency.
val secondaryCost : kotlin.Float = 3.4 // kotlin.Float | The cost of shipping to this country/region with another item, measured in the store's default currency.
val minProcessingTime : kotlin.Int = 56 // kotlin.Int | The minimum time required to process to ship listings with this shipping profile.
val maxProcessingTime : kotlin.Int = 56 // kotlin.Int | The maximum processing time the listing needs to ship.
val processingTimeUnit : kotlin.String = processingTimeUnit_example // kotlin.String | The unit used to represent how long a processing time is. A week is equivalent to the set processing schedule (default to 5 business days). If none is provided, the unit is set to \\\"business_days\\\".
val destinationCountryIso : kotlin.String = destinationCountryIso_example // kotlin.String | The ISO code of the country to which the listing ships. If null, request sets destination to destination_region. Required if destination_region is null or not provided.
val destinationRegion : kotlin.String = destinationRegion_example // kotlin.String | The code of the region to which the listing ships. A region represents a set of countries. Supported regions are Europe Union and Non-Europe Union (countries in Europe not in EU). If `none`, request sets destination to destination_country_iso. Required if destination_country_iso is null or not provided.
val originPostalCode : kotlin.String = originPostalCode_example // kotlin.String | The postal code string (not necessarily a number) for the location from which the listing ships. Required if the `origin_country_iso` supports postal codes. See the [Fulfillment Tutorial docs](https://developer.etsy.com/documentation/tutorials/fulfillment/#countries-requiring-postal-codes) for more info
val shippingCarrierId : kotlin.Int = 56 // kotlin.Int | The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with `mail_class`** if `min_delivery_days` and `max_delivery_days` are null.
val mailClass : kotlin.String = mailClass_example // kotlin.String | The unique ID string of a shipping carrier's mail class, which is used to calculate an estimated delivery date. **Required with `shipping_carrier_id`** if `min_delivery_days` and `max_delivery_days` are null.
val minDeliveryDays : kotlin.Int = 56 // kotlin.Int | The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `max_delivery_days`** if `mail_class` is null.
val maxDeliveryDays : kotlin.Int = 56 // kotlin.Int | The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `min_delivery_days`** if `mail_class` is null.
try {
    val result : ShopShippingProfile = apiInstance.createShopShippingProfile(shopId, title, originCountryIso, primaryCost, secondaryCost, minProcessingTime, maxProcessingTime, processingTimeUnit, destinationCountryIso, destinationRegion, originPostalCode, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#createShopShippingProfile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#createShopShippingProfile")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **title** | **kotlin.String**| The name string of this shipping profile. | |
| **originCountryIso** | **kotlin.String**| The ISO code of the country from which the listing ships. | |
| **primaryCost** | **kotlin.Float**| The cost of shipping to this country/region alone, measured in the store&#39;s default currency. | |
| **secondaryCost** | **kotlin.Float**| The cost of shipping to this country/region with another item, measured in the store&#39;s default currency. | |
| **minProcessingTime** | **kotlin.Int**| The minimum time required to process to ship listings with this shipping profile. | |
| **maxProcessingTime** | **kotlin.Int**| The maximum processing time the listing needs to ship. | |
| **processingTimeUnit** | **kotlin.String**| The unit used to represent how long a processing time is. A week is equivalent to the set processing schedule (default to 5 business days). If none is provided, the unit is set to \\\&quot;business_days\\\&quot;. | [optional] [default to business_days] [enum: business_days, weeks] |
| **destinationCountryIso** | **kotlin.String**| The ISO code of the country to which the listing ships. If null, request sets destination to destination_region. Required if destination_region is null or not provided. | [optional] |
| **destinationRegion** | **kotlin.String**| The code of the region to which the listing ships. A region represents a set of countries. Supported regions are Europe Union and Non-Europe Union (countries in Europe not in EU). If &#x60;none&#x60;, request sets destination to destination_country_iso. Required if destination_country_iso is null or not provided. | [optional] [default to none] [enum: eu, non_eu, none] |
| **originPostalCode** | **kotlin.String**| The postal code string (not necessarily a number) for the location from which the listing ships. Required if the &#x60;origin_country_iso&#x60; supports postal codes. See the [Fulfillment Tutorial docs](https://developer.etsy.com/documentation/tutorials/fulfillment/#countries-requiring-postal-codes) for more info | [optional] [default to &quot;&quot;] |
| **shippingCarrierId** | **kotlin.Int**| The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with &#x60;mail_class&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] [default to 0] |
| **mailClass** | **kotlin.String**| The unique ID string of a shipping carrier&#39;s mail class, which is used to calculate an estimated delivery date. **Required with &#x60;shipping_carrier_id&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] |
| **minDeliveryDays** | **kotlin.Int**| The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;max_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **maxDeliveryDays** | **kotlin.Int**| The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;min_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |

### Return type

[**ShopShippingProfile**](ShopShippingProfile.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="createShopShippingProfileDestination"></a>
# **createShopShippingProfileDestination**
> ShopShippingProfileDestination createShopShippingProfileDestination(shopId, shippingProfileId, primaryCost, secondaryCost, destinationCountryIso, destinationRegion, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Creates a new shipping destination, which sets the shipping cost, carrier, and class for a destination in a [shipping profile](/documentation/reference/#tag/Shop-ShippingProfile). createShopShippingProfileDestination assigns costs using the currency of the associated shop. Set the destination using either &#x60;destination_country_iso&#x60; or &#x60;destination_region&#x60;; &#x60;destination_country_iso&#x60; and &#x60;destination_region&#x60; are mutually exclusive — set one or the other. Setting both triggers error 400. If the request sets neither &#x60;destination_country_iso&#x60; nor &#x60;destination_region&#x60;, the default destination is \&quot;everywhere\&quot;. You must also either assign both a &#x60;shipping_carrier_id&#x60; AND &#x60;mail_class&#x60; or both &#x60;min_delivery_days&#x60; AND &#x60;max_delivery_days&#x60;.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
val primaryCost : kotlin.Float = 3.4 // kotlin.Float | The cost of shipping to this country/region alone, measured in the store's default currency.
val secondaryCost : kotlin.Float = 3.4 // kotlin.Float | The cost of shipping to this country/region with another item, measured in the store's default currency.
val destinationCountryIso : kotlin.String = destinationCountryIso_example // kotlin.String | The ISO code of the country to which the listing ships. If null, request sets destination to destination_region. Required if destination_region is null or not provided.
val destinationRegion : kotlin.String = destinationRegion_example // kotlin.String | The code of the region to which the listing ships. A region represents a set of countries. Supported regions are Europe Union and Non-Europe Union (countries in Europe not in EU). If `none`, request sets destination to destination_country_iso. Required if destination_country_iso is null or not provided.
val shippingCarrierId : kotlin.Int = 56 // kotlin.Int | The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with `mail_class`** if `min_delivery_days` and `max_delivery_days` are null.
val mailClass : kotlin.String = mailClass_example // kotlin.String | The unique ID string of a shipping carrier's mail class, which is used to calculate an estimated delivery date. **Required with `shipping_carrier_id`** if `min_delivery_days` and `max_delivery_days` are null.
val minDeliveryDays : kotlin.Int = 56 // kotlin.Int | The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `max_delivery_days`** if `mail_class` is null.
val maxDeliveryDays : kotlin.Int = 56 // kotlin.Int | The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `min_delivery_days`** if `mail_class` is null.
try {
    val result : ShopShippingProfileDestination = apiInstance.createShopShippingProfileDestination(shopId, shippingProfileId, primaryCost, secondaryCost, destinationCountryIso, destinationRegion, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#createShopShippingProfileDestination")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#createShopShippingProfileDestination")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |
| **primaryCost** | **kotlin.Float**| The cost of shipping to this country/region alone, measured in the store&#39;s default currency. | |
| **secondaryCost** | **kotlin.Float**| The cost of shipping to this country/region with another item, measured in the store&#39;s default currency. | |
| **destinationCountryIso** | **kotlin.String**| The ISO code of the country to which the listing ships. If null, request sets destination to destination_region. Required if destination_region is null or not provided. | [optional] |
| **destinationRegion** | **kotlin.String**| The code of the region to which the listing ships. A region represents a set of countries. Supported regions are Europe Union and Non-Europe Union (countries in Europe not in EU). If &#x60;none&#x60;, request sets destination to destination_country_iso. Required if destination_country_iso is null or not provided. | [optional] [default to none] [enum: eu, non_eu, none] |
| **shippingCarrierId** | **kotlin.Int**| The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with &#x60;mail_class&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] [default to 0] |
| **mailClass** | **kotlin.String**| The unique ID string of a shipping carrier&#39;s mail class, which is used to calculate an estimated delivery date. **Required with &#x60;shipping_carrier_id&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] |
| **minDeliveryDays** | **kotlin.Int**| The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;max_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **maxDeliveryDays** | **kotlin.Int**| The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;min_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |

### Return type

[**ShopShippingProfileDestination**](ShopShippingProfileDestination.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="createShopShippingProfileUpgrade"></a>
# **createShopShippingProfileUpgrade**
> ShopShippingProfileUpgrade createShopShippingProfileUpgrade(shopId, shippingProfileId, type, upgradeName, price, secondaryPrice, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Creates a new shipping profile upgrade, which can establish a price for a shipping option, such as an alternate carrier or faster delivery.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
val type : kotlin.String = type_example // kotlin.String | The type of the shipping upgrade. Domestic (0) or international (1).
val upgradeName : kotlin.String = upgradeName_example // kotlin.String | Name for the shipping upgrade shown to shoppers at checkout, e.g. USPS Priority.
val price : kotlin.Float = 3.4 // kotlin.Float | Additional cost of adding the shipping upgrade.
val secondaryPrice : kotlin.Float = 3.4 // kotlin.Float | Additional cost of adding the shipping upgrade for each additional item.
val shippingCarrierId : kotlin.Int = 56 // kotlin.Int | The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with `mail_class`** if `min_delivery_days` and `max_delivery_days` are null.
val mailClass : kotlin.String = mailClass_example // kotlin.String | The unique ID string of a shipping carrier's mail class, which is used to calculate an estimated delivery date. **Required with `shipping_carrier_id`** if `min_delivery_days` and `max_delivery_days` are null.
val minDeliveryDays : kotlin.Int = 56 // kotlin.Int | The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `max_delivery_days`** if `mail_class` is null.
val maxDeliveryDays : kotlin.Int = 56 // kotlin.Int | The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `min_delivery_days`** if `mail_class` is null.
try {
    val result : ShopShippingProfileUpgrade = apiInstance.createShopShippingProfileUpgrade(shopId, shippingProfileId, type, upgradeName, price, secondaryPrice, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#createShopShippingProfileUpgrade")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#createShopShippingProfileUpgrade")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |
| **type** | **kotlin.String**| The type of the shipping upgrade. Domestic (0) or international (1). | [enum: 0, 1] |
| **upgradeName** | **kotlin.String**| Name for the shipping upgrade shown to shoppers at checkout, e.g. USPS Priority. | |
| **price** | **kotlin.Float**| Additional cost of adding the shipping upgrade. | |
| **secondaryPrice** | **kotlin.Float**| Additional cost of adding the shipping upgrade for each additional item. | |
| **shippingCarrierId** | **kotlin.Int**| The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with &#x60;mail_class&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] [default to 0] |
| **mailClass** | **kotlin.String**| The unique ID string of a shipping carrier&#39;s mail class, which is used to calculate an estimated delivery date. **Required with &#x60;shipping_carrier_id&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] |
| **minDeliveryDays** | **kotlin.Int**| The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;max_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **maxDeliveryDays** | **kotlin.Int**| The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;min_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |

### Return type

[**ShopShippingProfileUpgrade**](ShopShippingProfileUpgrade.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="deleteShopShippingProfile"></a>
# **deleteShopShippingProfile**
> deleteShopShippingProfile(shopId, shippingProfileId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Deletes a ShippingProfile by given id.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
try {
    apiInstance.deleteShopShippingProfile(shopId, shippingProfileId)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#deleteShopShippingProfile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#deleteShopShippingProfile")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |

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

<a id="deleteShopShippingProfileDestination"></a>
# **deleteShopShippingProfileDestination**
> deleteShopShippingProfileDestination(shopId, shippingProfileId, shippingProfileDestinationId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Deletes a shipping destination and removes the destination option from every listing that uses the associated shipping profile. A shipping profile requires at least one shipping destination, so this endpoint cannot delete the final shipping destination for any shipping profile. To delete the final shipping destination from a shipping profile, you must [delete the entire shipping profile](/documentation/reference/#operation/deleteShopShippingProfile).

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
val shippingProfileDestinationId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the shipping profile destination in the [shipping profile](/documentation/reference#tag/Shop-ShippingProfile) associated with the listing.
try {
    apiInstance.deleteShopShippingProfileDestination(shopId, shippingProfileId, shippingProfileDestinationId)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#deleteShopShippingProfileDestination")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#deleteShopShippingProfileDestination")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shippingProfileDestinationId** | **kotlin.Long**| The numeric ID of the shipping profile destination in the [shipping profile](/documentation/reference#tag/Shop-ShippingProfile) associated with the listing. | |

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

<a id="deleteShopShippingProfileUpgrade"></a>
# **deleteShopShippingProfileUpgrade**
> deleteShopShippingProfileUpgrade(shopId, shippingProfileId, upgradeId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Deletes a shipping profile upgrade and removes the upgrade option from every listing that uses the associated shipping profile.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the shipping profile.
val upgradeId : kotlin.Long = 789 // kotlin.Long | The numeric ID that is associated with a shipping upgrade
try {
    apiInstance.deleteShopShippingProfileUpgrade(shopId, shippingProfileId, upgradeId)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#deleteShopShippingProfileUpgrade")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#deleteShopShippingProfileUpgrade")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the shipping profile. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **upgradeId** | **kotlin.Long**| The numeric ID that is associated with a shipping upgrade | |

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

<a id="getShippingCarriers"></a>
# **getShippingCarriers**
> ShippingCarriers getShippingCarriers(originCountryIso)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a list of available shipping carriers and the mail classes associated with them for a given country

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val originCountryIso : kotlin.String = originCountryIso_example // kotlin.String | The ISO code of the country from which the listing ships.
try {
    val result : ShippingCarriers = apiInstance.getShippingCarriers(originCountryIso)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#getShippingCarriers")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#getShippingCarriers")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **originCountryIso** | **kotlin.String**| The ISO code of the country from which the listing ships. | |

### Return type

[**ShippingCarriers**](ShippingCarriers.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopShippingProfile"></a>
# **getShopShippingProfile**
> ShopShippingProfile getShopShippingProfile(shopId, shippingProfileId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a Shipping Profile referenced by shipping profile ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
try {
    val result : ShopShippingProfile = apiInstance.getShopShippingProfile(shopId, shippingProfileId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#getShopShippingProfile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#getShopShippingProfile")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |

### Return type

[**ShopShippingProfile**](ShopShippingProfile.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopShippingProfileDestinationsByShippingProfile"></a>
# **getShopShippingProfileDestinationsByShippingProfile**
> ShopShippingProfileDestinations getShopShippingProfileDestinationsByShippingProfile(shopId, shippingProfileId, limit, offset)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a list of shipping destination objects associated with a shipping profile.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
val limit : kotlin.Int = 56 // kotlin.Int | The maximum number of results to return.
val offset : kotlin.Int = 56 // kotlin.Int | The number of records to skip before selecting the first result.
try {
    val result : ShopShippingProfileDestinations = apiInstance.getShopShippingProfileDestinationsByShippingProfile(shopId, shippingProfileId, limit, offset)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#getShopShippingProfileDestinationsByShippingProfile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#getShopShippingProfileDestinationsByShippingProfile")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |
| **limit** | **kotlin.Int**| The maximum number of results to return. | [optional] [default to 25] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **offset** | **kotlin.Int**| The number of records to skip before selecting the first result. | [optional] [default to 0] |

### Return type

[**ShopShippingProfileDestinations**](ShopShippingProfileDestinations.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopShippingProfileUpgrades"></a>
# **getShopShippingProfileUpgrades**
> ShopShippingProfileUpgrades getShopShippingProfileUpgrades(shopId, shippingProfileId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves the list of shipping profile upgrades assigned to a specific shipping profile.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
try {
    val result : ShopShippingProfileUpgrades = apiInstance.getShopShippingProfileUpgrades(shopId, shippingProfileId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#getShopShippingProfileUpgrades")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#getShopShippingProfileUpgrades")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |

### Return type

[**ShopShippingProfileUpgrades**](ShopShippingProfileUpgrades.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="getShopShippingProfiles"></a>
# **getShopShippingProfiles**
> ShopShippingProfiles getShopShippingProfiles(shopId)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Retrieves a list of shipping profiles available in the specific Etsy shop identified by its shop ID.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
try {
    val result : ShopShippingProfiles = apiInstance.getShopShippingProfiles(shopId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#getShopShippingProfiles")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#getShopShippingProfiles")
    e.printStackTrace()
}
```

### Parameters
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |

### Return type

[**ShopShippingProfiles**](ShopShippingProfiles.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a id="updateShopShippingProfile"></a>
# **updateShopShippingProfile**
> ShopShippingProfile updateShopShippingProfile(shopId, shippingProfileId, title, originCountryIso, minProcessingTime, maxProcessingTime, processingTimeUnit, originPostalCode)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Changes the settings in a shipping profile. You can pass a country iso code or a region when updating a ShippingProfile, but not both. Only one is required. You must pass either a shipping_carrier_id AND mail_class, or both min and max_delivery_days.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
val title : kotlin.String = title_example // kotlin.String | The name string of this shipping profile.
val originCountryIso : kotlin.String = originCountryIso_example // kotlin.String | The ISO code of the country from which the listing ships.
val minProcessingTime : kotlin.Int = 56 // kotlin.Int | The minimum time required to process to ship listings with this shipping profile.
val maxProcessingTime : kotlin.Int = 56 // kotlin.Int | The maximum processing time the listing needs to ship.
val processingTimeUnit : kotlin.String = processingTimeUnit_example // kotlin.String | The unit used to represent how long a processing time is. A week is equivalent to the set processing schedule (default to 5 business days). If none is provided, the unit is set to \\\"business_days\\\".
val originPostalCode : kotlin.String = originPostalCode_example // kotlin.String | The postal code string (not necessarily a number) for the location from which the listing ships. Required if the `origin_country_iso` supports postal codes. See the [Fulfillment Tutorial docs](https://developer.etsy.com/documentation/tutorials/fulfillment/#countries-requiring-postal-codes) for more info
try {
    val result : ShopShippingProfile = apiInstance.updateShopShippingProfile(shopId, shippingProfileId, title, originCountryIso, minProcessingTime, maxProcessingTime, processingTimeUnit, originPostalCode)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#updateShopShippingProfile")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#updateShopShippingProfile")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |
| **title** | **kotlin.String**| The name string of this shipping profile. | [optional] |
| **originCountryIso** | **kotlin.String**| The ISO code of the country from which the listing ships. | [optional] |
| **minProcessingTime** | **kotlin.Int**| The minimum time required to process to ship listings with this shipping profile. | [optional] |
| **maxProcessingTime** | **kotlin.Int**| The maximum processing time the listing needs to ship. | [optional] |
| **processingTimeUnit** | **kotlin.String**| The unit used to represent how long a processing time is. A week is equivalent to the set processing schedule (default to 5 business days). If none is provided, the unit is set to \\\&quot;business_days\\\&quot;. | [optional] [default to business_days] [enum: business_days, weeks] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **originPostalCode** | **kotlin.String**| The postal code string (not necessarily a number) for the location from which the listing ships. Required if the &#x60;origin_country_iso&#x60; supports postal codes. See the [Fulfillment Tutorial docs](https://developer.etsy.com/documentation/tutorials/fulfillment/#countries-requiring-postal-codes) for more info | [optional] |

### Return type

[**ShopShippingProfile**](ShopShippingProfile.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="updateShopShippingProfileDestination"></a>
# **updateShopShippingProfileDestination**
> ShopShippingProfileDestination updateShopShippingProfileDestination(shopId, shippingProfileId, shippingProfileDestinationId, primaryCost, secondaryCost, destinationCountryIso, destinationRegion, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates an existing shipping destination, which can set or reassign the shipping cost, carrier, and class for a destination.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
val shippingProfileDestinationId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the shipping profile destination in the [shipping profile](/documentation/reference#tag/Shop-ShippingProfile) associated with the listing.
val primaryCost : kotlin.Float = 3.4 // kotlin.Float | The cost of shipping to this country/region alone, measured in the store's default currency.
val secondaryCost : kotlin.Float = 3.4 // kotlin.Float | The cost of shipping to this country/region with another item, measured in the store's default currency.
val destinationCountryIso : kotlin.String = destinationCountryIso_example // kotlin.String | The ISO code of the country to which the listing ships. If null, request sets destination to destination_region. Required if destination_region is null or not provided.
val destinationRegion : kotlin.String = destinationRegion_example // kotlin.String | The code of the region to which the listing ships. A region represents a set of countries. Supported regions are Europe Union and Non-Europe Union (countries in Europe not in EU). If `none`, request sets destination to destination_country_iso. Required if destination_country_iso is null or not provided.
val shippingCarrierId : kotlin.Int = 56 // kotlin.Int | The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with `mail_class`** if `min_delivery_days` and `max_delivery_days` are null.
val mailClass : kotlin.String = mailClass_example // kotlin.String | The unique ID string of a shipping carrier's mail class, which is used to calculate an estimated delivery date. **Required with `shipping_carrier_id`** if `min_delivery_days` and `max_delivery_days` are null.
val minDeliveryDays : kotlin.Int = 56 // kotlin.Int | The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `max_delivery_days`** if `mail_class` is null.
val maxDeliveryDays : kotlin.Int = 56 // kotlin.Int | The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `min_delivery_days`** if `mail_class` is null.
try {
    val result : ShopShippingProfileDestination = apiInstance.updateShopShippingProfileDestination(shopId, shippingProfileId, shippingProfileDestinationId, primaryCost, secondaryCost, destinationCountryIso, destinationRegion, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#updateShopShippingProfileDestination")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#updateShopShippingProfileDestination")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |
| **shippingProfileDestinationId** | **kotlin.Long**| The numeric ID of the shipping profile destination in the [shipping profile](/documentation/reference#tag/Shop-ShippingProfile) associated with the listing. | |
| **primaryCost** | **kotlin.Float**| The cost of shipping to this country/region alone, measured in the store&#39;s default currency. | [optional] |
| **secondaryCost** | **kotlin.Float**| The cost of shipping to this country/region with another item, measured in the store&#39;s default currency. | [optional] |
| **destinationCountryIso** | **kotlin.String**| The ISO code of the country to which the listing ships. If null, request sets destination to destination_region. Required if destination_region is null or not provided. | [optional] |
| **destinationRegion** | **kotlin.String**| The code of the region to which the listing ships. A region represents a set of countries. Supported regions are Europe Union and Non-Europe Union (countries in Europe not in EU). If &#x60;none&#x60;, request sets destination to destination_country_iso. Required if destination_country_iso is null or not provided. | [optional] [default to none] [enum: eu, non_eu, none] |
| **shippingCarrierId** | **kotlin.Int**| The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with &#x60;mail_class&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] |
| **mailClass** | **kotlin.String**| The unique ID string of a shipping carrier&#39;s mail class, which is used to calculate an estimated delivery date. **Required with &#x60;shipping_carrier_id&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] |
| **minDeliveryDays** | **kotlin.Int**| The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;max_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **maxDeliveryDays** | **kotlin.Int**| The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;min_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |

### Return type

[**ShopShippingProfileDestination**](ShopShippingProfileDestination.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

<a id="updateShopShippingProfileUpgrade"></a>
# **updateShopShippingProfileUpgrade**
> ShopShippingProfileUpgrade updateShopShippingProfileUpgrade(shopId, shippingProfileId, upgradeId, upgradeName, type, price, secondaryPrice, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)



&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;span class&#x3D;\&quot;wt-badge wt-badge--notificationPrimary wt-bg-slime-tint wt-mr-xs-2\&quot;&gt;General Release&lt;/span&gt;&lt;a class&#x3D;\&quot;wt-text-link\&quot; href&#x3D;\&quot;https://github.com/etsy/open-api/discussions\&quot; target&#x3D;\&quot;_blank\&quot; rel&#x3D;\&quot;noopener noreferrer\&quot;&gt;Report bug&lt;/a&gt;&lt;/div&gt;&lt;div class&#x3D;\&quot;wt-display-flex-xs wt-align-items-center wt-mt-xs-2 wt-mb-xs-3\&quot;&gt;&lt;p class&#x3D;\&quot;wt-text-body-01 banner-text\&quot;&gt;This endpoint is ready for production use.&lt;/p&gt;&lt;/div&gt;  Updates a shipping profile upgrade and updates any listings that use the shipping profile.

### Example
```kotlin
// Import classes:
//import com.etsy.infrastructure.*
//import com.etsy.models.*

val apiInstance = ShopShippingProfileApi()
val shopId : kotlin.Long = 789 // kotlin.Long | The unique positive non-zero numeric ID for an Etsy Shop.
val shippingProfileId : kotlin.Long = 789 // kotlin.Long | The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is `physical`.
val upgradeId : kotlin.Long = 789 // kotlin.Long | The numeric ID that is associated with a shipping upgrade
val upgradeName : kotlin.String = upgradeName_example // kotlin.String | Name for the shipping upgrade shown to shoppers at checkout, e.g. USPS Priority.
val type : kotlin.String = type_example // kotlin.String | The type of the shipping upgrade. Domestic (0) or international (1).
val price : kotlin.Float = 3.4 // kotlin.Float | Additional cost of adding the shipping upgrade.
val secondaryPrice : kotlin.Float = 3.4 // kotlin.Float | Additional cost of adding the shipping upgrade for each additional item.
val shippingCarrierId : kotlin.Int = 56 // kotlin.Int | The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with `mail_class`** if `min_delivery_days` and `max_delivery_days` are null.
val mailClass : kotlin.String = mailClass_example // kotlin.String | The unique ID string of a shipping carrier's mail class, which is used to calculate an estimated delivery date. **Required with `shipping_carrier_id`** if `min_delivery_days` and `max_delivery_days` are null.
val minDeliveryDays : kotlin.Int = 56 // kotlin.Int | The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `max_delivery_days`** if `mail_class` is null.
val maxDeliveryDays : kotlin.Int = 56 // kotlin.Int | The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with `min_delivery_days`** if `mail_class` is null.
try {
    val result : ShopShippingProfileUpgrade = apiInstance.updateShopShippingProfileUpgrade(shopId, shippingProfileId, upgradeId, upgradeName, type, price, secondaryPrice, shippingCarrierId, mailClass, minDeliveryDays, maxDeliveryDays)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling ShopShippingProfileApi#updateShopShippingProfileUpgrade")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling ShopShippingProfileApi#updateShopShippingProfileUpgrade")
    e.printStackTrace()
}
```

### Parameters
| **shopId** | **kotlin.Long**| The unique positive non-zero numeric ID for an Etsy Shop. | |
| **shippingProfileId** | **kotlin.Long**| The numeric ID of the [shipping profile](/documentation/reference#operation/getShopShippingProfile) associated with the listing. Required when listing type is &#x60;physical&#x60;. | |
| **upgradeId** | **kotlin.Long**| The numeric ID that is associated with a shipping upgrade | |
| **upgradeName** | **kotlin.String**| Name for the shipping upgrade shown to shoppers at checkout, e.g. USPS Priority. | [optional] |
| **type** | **kotlin.String**| The type of the shipping upgrade. Domestic (0) or international (1). | [optional] [enum: 0, 1] |
| **price** | **kotlin.Float**| Additional cost of adding the shipping upgrade. | [optional] |
| **secondaryPrice** | **kotlin.Float**| Additional cost of adding the shipping upgrade for each additional item. | [optional] |
| **shippingCarrierId** | **kotlin.Int**| The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with &#x60;mail_class&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] |
| **mailClass** | **kotlin.String**| The unique ID string of a shipping carrier&#39;s mail class, which is used to calculate an estimated delivery date. **Required with &#x60;shipping_carrier_id&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. | [optional] |
| **minDeliveryDays** | **kotlin.Int**| The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;max_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |
| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **maxDeliveryDays** | **kotlin.Int**| The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;min_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. | [optional] |

### Return type

[**ShopShippingProfileUpgrade**](ShopShippingProfileUpgrade.md)

### Authorization


Configure api_key:
    ApiClient.apiKey["x-api-key"] = ""
    ApiClient.apiKeyPrefix["x-api-key"] = ""
Configure oauth2:
    ApiClient.accessToken = ""

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

