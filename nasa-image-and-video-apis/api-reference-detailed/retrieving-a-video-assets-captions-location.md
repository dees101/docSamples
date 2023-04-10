---
description: Retrieving a video asset’s captions location
---

# Retrieving a video asset’s captions location

GET /captions/{nasa\_id}

#### Parameters:

| Name     | Type   | Description                |
| -------- | ------ | -------------------------- |
| nasa\_id | string | The video asset’s NASA ID. |

#### Example Request:

{% code overflow="wrap" %}
```markup
curl https://images-api.nasa.gov/captions/172_ISS-Slosh |
 python -m json.tool
```
{% endcode %}

#### Example Response:

{% code overflow="wrap" %}
```markup
{
"location": "https://images-assets.nasa.gov/video/172_ISS-Slosh/172_ISS-Slosh.srt"
}
```
{% endcode %}

Download the VTT or SRT file at the location in the response to see the video’s captions.

