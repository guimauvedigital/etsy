
# ShopShippingProfileDestination

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **shippingProfileDestinationId** | **kotlin.Long** | The numeric ID of the shipping profile destination in the [shipping profile](/documentation/reference#tag/Shop-ShippingProfile) associated with the listing. |  [optional] |
| **shippingProfileId** | **kotlin.Long** | The numeric ID of the shipping profile. |  [optional] |
| **originCountryIso** | **kotlin.String** | The ISO code of the country from which the listing ships. |  [optional] |
| **destinationCountryIso** | **kotlin.String** | The ISO code of the country to which the listing ships. If null, request sets destination to destination_region. Required if destination_region is null or not provided. |  [optional] |
| **destinationRegion** | [**inline**](#DestinationRegion) | The code of the region to which the listing ships. A region represents a set of countries. Supported regions are Europe Union and Non-Europe Union (countries in Europe not in EU). If &#x60;none&#x60;, request sets destination to destination_country_iso. Required if destination_country_iso is null or not provided. |  [optional] |
| **primaryCost** | [**Money**](Money.md) | The cost of shipping to this country/region alone, measured in the store&#39;s default currency. |  [optional] |
| **secondaryCost** | [**Money**](Money.md) | The cost of shipping to this country/region with another item, measured in the store&#39;s default currency. |  [optional] |
| **shippingCarrierId** | **kotlin.Int** | The unique ID of a supported shipping carrier, which is used to calculate an Estimated Delivery Date. **Required with &#x60;mail_class&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. |  [optional] |
| **mailClass** | **kotlin.String** | The unique ID string of a shipping carrier&#39;s mail class, which is used to calculate an estimated delivery date. **Required with &#x60;shipping_carrier_id&#x60;** if &#x60;min_delivery_days&#x60; and &#x60;max_delivery_days&#x60; are null. |  [optional] |
| **minDeliveryDays** | **kotlin.Int** | The minimum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;max_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. |  [optional] |
| **maxDeliveryDays** | **kotlin.Int** | The maximum number of business days a buyer can expect to wait to receive their purchased item once it has shipped. **Required with &#x60;min_delivery_days&#x60;** if &#x60;mail_class&#x60; is null. |  [optional] |


<a id="DestinationRegion"></a>
## Enum: destination_region
| Name | Value |
| ---- | ----- |
| destinationRegion | eu, non_eu, none |



