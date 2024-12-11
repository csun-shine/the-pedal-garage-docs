---
layout: page
---

# API Reference: Retrieve All Songs

Retrieve all [`songs`](pg-resource-songs.md) in the database.

## Endpoint

To retrieve all songs in the databse, use the `GET /songs` endpoint.

## Request Example

```shell
curl -X GET http://localhost:3000/songs
```

## Return Body Example

```shell
[
      {
        "id": 1, 
        "name": "Just Like Heaven",
        "artist": "The Cure",
        "year": 1987,
        "label": "Fiction", 
        "pedalIDs": [6,7]
      },
      {
        "id": 2, 
        "name": "New Year's Day",
        "artist": "U2",
        "year": 1983,
        "label": "Island", 
        "pedalIDs": [5,8]
      },
      {
        "id": 3, 
        "name": "That Lady, Pts. 1 & 2",
        "artist": "The Isley Brothers",
        "year": "1964",
        "label": "United Artists", 
        "pedalIDs": [1,2]
      } 
    ...
]
```

## Resource Properties

| Name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The ID of the song resource to which pedals are attached |
| `name` | string | The name of the song |
| `artist` | string | The name of the artist |
| `year` | number | The year the song was released |
| `label` | string | The label that published the song |
| `pedalIDs` | number | The pedal IDs attached to this particular song resource |

## Common Response Codes

| Status Code      | Category       | Description | Troubleshooting Tips |
|------------------|----------------|-------------|----------------------|
| 200 OK           | Success        | The request was successful. | Not Applicable |
| 201 Created      | Success        | A resource was successfully created. | Not Applicable |
| 204 No Content   | Success        | The request succeeded, but no content is returned. | Check the API documentation if content is expected. |
| 400 Bad Request  | Error   | The server could not understand the request. | Check for malformed syntax, invalid input, or missing fields in the request. |
| 404 Not Found    | Error   | The resource could not be found. | Confirm the URL is correct and the resource exists. |
| 500 Internal Server Error | Error | A generic error occurred on the server. | Start the service and try again. |
| ECONNREFUSED | Error | Service is offline. | Start the service and try again. |

## Related Topics

* [`Songs`](pg-resource-songs.md)
* [`Get song by ID`](pg-reference-get-song-by-id.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)

## Need Help?

We're here to help! For assistance, feel free to contact developer support at pedalgaragesupport@example.com.