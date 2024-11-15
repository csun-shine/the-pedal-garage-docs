---
layout: page
---

# API Reference

Returns all [`pedals`](pedal.md) within the database.

## URL

```shell
{base_url}/pedals
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
        "make": "Electro-Harmonix",
        "model": "Big Muff",
        "trim": "Ram's Head",
        "family": "fuzz",
        "songIDs": [3]
      }
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

* [`Pedals`](pedal.md)
* [`Get pedals by ID`](get-pedals-by-ID.md)
* [`Get songs by ID`](get-songs-by-id.md)
