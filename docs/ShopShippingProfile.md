
# ShopShippingProfile

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **shippingProfileId** | **kotlin.Long** | The numeric ID of the shipping profile. |  [optional] |
| **title** | **kotlin.String** | The name string of this shipping profile. |  [optional] |
| **userId** | **kotlin.Long** | The numeric ID for the [user](/documentation/reference#tag/User) who owns the shipping profile. |  [optional] |
| **minProcessingDays** | **kotlin.Int** | The minimum number of days for processing the listing. |  [optional] |
| **maxProcessingDays** | **kotlin.Int** | The maximum number of days for processing the listing. |  [optional] |
| **processingDaysDisplayLabel** | **kotlin.String** | Translated display label string for processing days. |  [optional] |
| **originCountryIso** | **kotlin.String** | The ISO code of the country from which the listing ships. |  [optional] |
| **isDeleted** | **kotlin.Boolean** | When true, someone deleted this shipping profile. |  [optional] |
| **shippingProfileDestinations** | [**kotlin.collections.List&lt;ShopShippingProfileDestination&gt;**](ShopShippingProfileDestination.md) | A list of [shipping profile destinations](/documentation/reference/#operation/createShopShippingProfileDestination) available for this shipping profile. |  [optional] |
| **shippingProfileUpgrades** | [**kotlin.collections.List&lt;ShopShippingProfileUpgrade&gt;**](ShopShippingProfileUpgrade.md) | A list of [shipping profile upgrades](/documentation/reference/#operation/createShopShippingProfileUpgrade) available for this shipping profile. |  [optional] |
| **originPostalCode** | **kotlin.String** | The postal code string (not necessarily a number) for the location from which the listing ships. Required if the &#x60;origin_country_iso&#x60; supports postal codes. See the [Fulfillment Tutorial docs](https://developer.etsy.com/documentation/tutorials/fulfillment/#countries-requiring-postal-codes) for more info |  [optional] |
| **profileType** | [**inline**](#ProfileType) |  |  [optional] |
| **domesticHandlingFee** | **kotlin.Float** | The domestic handling fee added to buyer&#39;s shipping total - only available for calculated shipping profiles. |  [optional] |
| **internationalHandlingFee** | **kotlin.Float** | The international handling fee added to buyer&#39;s shipping total - only available for calculated shipping profiles. |  [optional] |


<a id="ProfileType"></a>
## Enum: profile_type
| Name | Value |
| ---- | ----- |
| profileType | manual, calculated |



