---
layout: page
---

# API Reference

Returns a [`song`](songs.md) array that contains only the pedal resource specified by the `id` parameter, if it exists.

## URL

```shell
{base_url}/songs/{id}
```

## Parameters

| Parameter name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The song's unique record ID |

## Request headers

Content-Type: application/json

## Request body

None

## Return body

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
    ...
]
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

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

* [`Songs`](song.md)
* [`Get all songs`](pg-reference-get-all-songs.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)
