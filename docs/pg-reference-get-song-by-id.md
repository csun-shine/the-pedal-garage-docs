---
layout: page
---

# API Reference

Returns a [`song`](song.md) array that contains only the pedal resource specified by the `id` parameter, if it exists.

## URL

```shell
{base_url}/songs/{id}
```

## Params

| Parameter name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The song's unique record ID |

## Request headers

None

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

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

* [`Songs`](song.md)
* [`Get all songs`](get-all-songs.md)
* [`Get pedals by ID`](songs-get-pedals-by-id.md)
