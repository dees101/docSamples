# Retrieving a media asset’s manifest

## Retrieving a media asset’s manifest&#x20;

GET /asset/{nasa\_id}&#x20;

#### Parameters:

| Name     | Type   | Description                |
| -------- | ------ | -------------------------- |
| nasa\_id | string | The media asset’s NASA ID. |

#### Example Request:

{% code overflow="wrap" %}
```markup
curl https://images-api.nasa.gov/asset/as11-40-5874 |
 python -m json.tool
```
{% endcode %}

#### Example Response:

Asset manifest results will come in the form of [Collection+JSON](https://github.com/collection-json/spec):

```markup


{
"collection": {
"href": "https://images-api.nasa.gov/asset/as11-40-5874",
"items": [
{
"href": "https://images-assets.nasa.gov/image/as11-40-5874/as11-40-5874~orig.jpg"
},
{
"href": "https://images-assets.nasa.gov/image/as11-40-5874/as11‐40‐5874~medium.jpg"
},
{
"href": "https://images-assets.nasa.gov/image/as11-40-5874/as11‐40‐5874~small.jpg"
},
{
"href": "https://images-assets.nasa.gov/image/as11-40-5874/as11‐40‐5874~thumb.jpg"
},
{
"href": "https://images-assets.nasa.gov/image/as11-40-5874/metadata.json"
}
],
"version": "1.0"
}
}

```
