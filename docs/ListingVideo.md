
# ListingVideo

## Properties
| Name | Type | Description | Notes |
| ------------ | ------------- | ------------- | ------------- |
| **videoId** | **kotlin.Long** | The unique ID of a video associated with a listing. |  [optional] |
| **height** | **kotlin.Int** | The video height dimension in pixels. |  [optional] |
| **width** | **kotlin.Int** | The video width dimension in pixels. |  [optional] |
| **thumbnailUrl** | **kotlin.String** | The url of the video thumbnail. |  [optional] |
| **videoUrl** | **kotlin.String** | The url of the video file. |  [optional] |
| **videoState** | [**inline**](#VideoState) | The current state of a given video. Value is one of &#x60;active&#x60;, &#x60;inactive&#x60;, &#x60;deleted&#x60; or &#x60;flagged&#x60;. |  [optional] |


<a id="VideoState"></a>
## Enum: video_state
| Name | Value |
| ---- | ----- |
| videoState | active, inactive, deleted, flagged |



