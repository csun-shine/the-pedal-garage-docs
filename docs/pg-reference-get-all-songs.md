---
layout: page
---

# API Reference

Returns all [`songs`](songs.md) in the database.

## URL

```shell
{base_url}/songs
```

## Return Parameters

| Name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The ID of the song resource to which pedals are attached |
| `name` | string | The name of the song |
| `artist` | string | The name of the artist |
| `year` | number | The year the song was released |
| `label` | string | The label that published the song |
| `pedalIDs` | number | The pedal IDs attached to this particular song resource |

## Request Headers

Content-Type: application/json

## Request Body Example

None

## Return Body Example

```js
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

## Return Status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

* [`Songs`](song.md)
* [`Get song by ID`](pg-reference-get-song-by-id.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)
