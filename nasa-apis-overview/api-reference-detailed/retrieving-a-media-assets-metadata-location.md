---
description: Retrieving a media asset’s metadata location
---

# Retrieving a media asset’s metadata location

GET /metadata/{nasa\_id}&#x20;

#### Parameters:

| Name     | Type   | Description                |
| -------- | ------ | -------------------------- |
| nasa\_id | string | The media asset’s NASA ID. |

#### Example Request:

{% code overflow="wrap" %}
```markup
curl https://images-api.nasa.gov/metadata/as11-40-5874 |
 python -m json.tool
```
{% endcode %}

#### Example Response:

{% code overflow="wrap" %}
```markup
{
"location": "https://images-assets.nasa.gov/image/as11-40-5874/metadata.json"
}
```
{% endcode %}

Download the JSON file at the location in the response to see the asset’s metadata.

