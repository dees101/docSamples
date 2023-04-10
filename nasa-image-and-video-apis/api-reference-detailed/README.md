---
description: Nasa Images and Video API
---

# API Reference (detailed)

### Performing a search

GET /search?q={q}

#### Parameters:

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

&#x20;                                                                                                          &#x20;

