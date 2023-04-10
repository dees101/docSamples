# Performing a search

## Performing a search

GET /search?q={q}

#### Parameters:&#x20;

| Name                                                                           | Type   | Description                                                                                                        |
| ------------------------------------------------------------------------------ | ------ | ------------------------------------------------------------------------------------------------------------------ |
| q (optional) string Free text search terms to compare to all indexed metadata. | string | Free text search terms to compare to all indexed metadata.                                                         |
| center (optional)                                                              | string | NASA center which published the media.                                                                             |
| description (optional)                                                         | string | Terms to search for in “Description” fields.                                                                       |
| description\_508 (optional)                                                    | string | Terms to search for in “508 Description” fields.                                                                   |
| keywords (optional)                                                            | string | Terms to search for in “Keywords” fields. Separate multiple values with commas.                                    |
| location (optional)                                                            | string | Terms to search for in “Location” fields.                                                                          |
| media\_type (optional)                                                         | string | Media types to restrict the search to. Available types: \[“image”, “audio”]. Separate multiple values with commas. |
| nasa\_id (optional)                                                            | string | The media asset’s NASA ID.                                                                                         |
| page (optional)                                                                | string | Page number, starting at 1, of results to get.                                                                     |
| page\_size (optional)                                                          | string | Number of results per page. Default: 100.                                                                          |
| photographer (optional)                                                        | string | The primary photographer’s name.                                                                                   |
| secondary\_creator (optional)                                                  | string | A secondary photographer/videographer’s name.                                                                      |
| title (optional)                                                               | string | Terms to search for in “Title” fields.                                                                             |
| year\_start (optional)                                                         | string | The start year for results. Format: YYYY.                                                                          |
| year\_end (optional)                                                           | string | The end year for results. Format: YYYY.                                                                            |

#### Example Request:&#x20;

{% code overflow="wrap" %}
```markup
At least one parameter is required, but all individual parameters are optional. All parameter values must be URLencoded. Most HTTP client libraries will take care of this for you. Use --data-urlencode to encode values using curl: 

 curl -G https://images-api.nasa.gov/search
     --data-urlencode "q=apollo 11"
     --data-urlencode "description=moon landing"
     --data-urlencode "media_type=image" |
     python -m json.tool   
     
The equivalent pre-encoded request looks more typical:
        
 curl "https://images-api.nasa.gov/search
      ?q=apollo%2011
      &description=moon%20landing
      &media_type=image" |
      python -m json.tool   
      
```
{% endcode %}

#### Example Response:&#x20;

Search results will come in the form of [Collection+JSON](https://github.com/collection-json/spec), which contains results and information about how to retrieve more details about each result:

{% code overflow="wrap" %}
```markup


{
 "collection": {
 "href": "https://images-api.nasa.gov/search?q=apollo%2011...",
 "items": [
 {
 "data": [
 {
 "center": "JSC",
 "date_created": "1969-07-21T00:00:00Z",
 "description": "AS11-40-5874 (20 July 1969) ---
 Astronaut Edwin E. Aldrin Jr., lunar module pilot
 of the first lunar landing mission, poses for a
 photograph beside the deployed United States flag
 during Apollo 11 extravehicular activity (EVA) on
 the lunar surface. The Lunar Module (LM) is on the
 left, and the footprints of the astronauts are
 clearly visible in the soil of the moon. Astronaut
 Neil A. Armstrong, commander, took this picture
 with a 70mm Hasselblad lunar surface camera. While
 astronauts Armstrong and Aldrin descended in the LM
 the \"Eagle\" to explore the Sea of Tranquility
 region of the moon, astronaut Michael Collins,
 command module pilot, remained with the Command and
 Service Modules (CSM) \"Columbia\" in lunar
 orbit.",
 "keywords": [
 "APOLLO 11 FLIGHT",
 "MOON",
 "LUNAR SURFACE",
 "LUNAR BASES",
 "LUNAR MODULE",
 "ASTRONAUTS",
 "EXTRAVEHICULAR ACIVITY"
 ],
 "media_type": "image",
 "nasa_id": "as11-40-5874",
 "title": "Apollo 11 Mission image - Astronaut Edwin Aldrin
 poses beside th"
 }
 ],
 "href": "https://images-assets.nasa.gov/image/as11-40-5874/collection.json",
 "links": [
 {
 "href": "https://images-assets.nasa.gov/image/as11-40-5874/as11-40-5874~thumb.jpg",
 "rel": "preview",
 "render": "image"
 }
 ]
 }
 ...*99 more objects omitted*...
 ],"links": [
 {
 "href": "https://images-api.nasa.gov/search?q=apollo+11...&page=2",
 "prompt": "Next",
 "rel": "next"
 }
 ],
 "metadata": {
 "total_hits": 336
 },
 "version": "1.0"
 }
}
```
{% endcode %}
