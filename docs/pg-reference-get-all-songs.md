---
layout: page
---

# API Reference

Returns all [`songs`](song.md) in the database.

## URL

```shell
{base_url}/songs
```

## Params

None

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
* [`Get songs by ID`](get-songs-by-id.md)
* [`Get pedals by ID`](get-pedals-by-id.md)
