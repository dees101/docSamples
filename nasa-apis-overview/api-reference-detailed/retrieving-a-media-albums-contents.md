# Retrieving a media album’s contents

## Retrieving a media album’s contents&#x20;

GET /album/album\_name

#### &#x20;Parameters:

| Name            | Type    | Description                                    |
| --------------- | ------- | ---------------------------------------------- |
| album\_name     | string  | The media album’s name (case-sensitive).       |
| page (optional) | integer | Page number, starting at 1, of results to get. |

#### Example Request:

{% code overflow="wrap" %}
```markup
curl https://images-api.nasa.gov/album/apollo |
 python -m json.tool
```
{% endcode %}



#### Example Response:

<pre class="language-markup" data-overflow="wrap"><code class="lang-markup"><strong>
</strong>Like search results, album contents will come in the form of <a data-footnote-ref href="#user-content-fn-1">Collection+JSON</a>, which contains results and information about how to retrieve more details about each member:

{
"collection": {
"href": "https://images-api.nasa.gov/album/apollo",
"items": [
{
"data": [
{
"nasa_id": "GSFC_20171102_Archive_e000579",
"album": [
"apollo"
],
"keywords": [
"NASA",
"GSFC",
"Space Technology Demo at NASA Wallops"
],
"title": "Space Technology Demo at NASA Wallops",
"media_type": "image",
"date_created": "2017-11-06T00:00:00Z",
"center": "GSFC",
"description": "A Black Brant IX suborbital sounding rocket is launched at 7:07 p.m., W}
],
"href": "https://images-assets.nasa.gov/image/GSFC_20171102_Archive_e000579/collection.json"links": [
{
"href": "https://images-assets.nasa.gov/image/GSFC_20171102_Archive_e000579/GSFC_20"rel": "preview",
"render": "image"
}
]
},
...*99 more objects omitted*...
],
"links": [
{
"href": "https://images-api.nasa.gov/album/apollo?page=2",
"prompt": "Next",
"rel": "next"
}
],
"metadata": {
"total_hits": 302
},
"version": "1.0"
}
}

</code></pre>

[^1]: [https://github.com/collection-json/spec](https://github.com/collection-json/spec)
