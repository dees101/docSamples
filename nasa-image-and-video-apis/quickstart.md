# Quickstart

## NASA Image and Video Library API

This quickstart shows you how to access NASA Image and Video Library APIs at [images.nasa.gov](https://https/images.nasa.gov).

#### Prerequistes:

You can use the DEMO\_KEY to explore the APIs on a limited basis. (See rate limits [here](https://api.nasa.gov))

Users planning to use the APIs intensively can sign up for an API developer key [here](https://api.nasa.gov).

You can access these APIs via these standard REST API calls.

#### API Error Codes

images-api.nasa.gov uses conventional HTTP response codes to indicate the success or failure of an API request.

#### HTTP status code summary

| Code                               | Explanation                                                              |
| ---------------------------------- | ------------------------------------------------------------------------ |
| 200 - OK                           | Everything worked as expected.                                           |
| 400 - Bad Request                  | The request was unacceptable, often due to missing a required parameter. |
| 404 - Not Found                    | The requested resource doesn’t exist.                                    |
| 500, 502, 503, 504 - Server Errors | Something went wrong on the API’s end. (These are rare.)                 |

##
