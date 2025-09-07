
# ListingImage

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **listingId** | **kotlin.Long** | The numeric ID for the [listing](/documentation/reference#tag/ShopListing) associated to this transaction. |  [optional] |
| **listingImageId** | **kotlin.Long** | The numeric ID of the primary [listing image](/documentation/reference#tag/ShopListing-Image) for this transaction. |  [optional] |
| **hexCode** | **kotlin.String** | The webhex string for the image&#39;s average color, in webhex notation. |  [optional] |
| **red** | **kotlin.Int** | The numeric red value equal to the image&#39;s average red value, from 0-255 (RGB color). |  [optional] |
| **green** | **kotlin.Int** | The numeric red value equal to the image&#39;s average red value, from 0-255 (RGB color). |  [optional] |
| **blue** | **kotlin.Int** | The numeric red value equal to the image&#39;s average red value, from 0-255 (RGB color). |  [optional] |
| **hue** | **kotlin.Int** | The numeric hue equal to the image&#39;s average hue, from 0-360 (HSV color). |  [optional] |
| **saturation** | **kotlin.Int** | The numeric saturation equal to the image&#39;s average saturation, from 0-100 (HSV color). |  [optional] |
| **brightness** | **kotlin.Int** | The numeric brightness equal to the image&#39;s average brightness, from 0-100 (HSV color). |  [optional] |
| **isBlackAndWhite** | **kotlin.Boolean** | When true, the image is in black &amp; white. |  [optional] |
| **creationTsz** | **kotlin.Int** | The listing image&#39;s creation time, in epoch seconds. |  [optional] |
| **createdTimestamp** | **kotlin.Int** | The listing image&#39;s creation time, in epoch seconds. |  [optional] |
| **rank** | **kotlin.Int** | The positive non-zero numeric position in the images displayed in a listing, with rank 1 images appearing in the left-most position in a listing. |  [optional] |
| **url75x75** | **kotlin.String** | The url string for a 75x75 pixel thumbnail of the image. |  [optional] |
| **url170x135** | **kotlin.String** | The url string for a 170x135 pixel thumbnail of the image. |  [optional] |
| **url570xN** | **kotlin.String** | The url string for a thumbnail of the image, no more than 570 pixels wide with variable height. |  [optional] |
| **urlFullxfull** | **kotlin.String** | The url string for the full-size image, up to 3000 pixels in each dimension. |  [optional] |
| **fullHeight** | **kotlin.Int** | The numeric height, measured in pixels, of the full-sized image referenced in url_fullxfull. |  [optional] |
| **fullWidth** | **kotlin.Int** | The numeric width, measured in pixels, of the full-sized image referenced in url_fullxfull. |  [optional] |
| **altText** | **kotlin.String** | Alt text for the listing image. Max length 500 characters. |  [optional] |



