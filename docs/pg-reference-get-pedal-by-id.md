---
layout: page
---

# API Reference

Returns a [`pedal`](pedal.md) array that contains only the pedal resource specified by the `id` parameter, if it exists.

## URL

```shell
{base_url}/pedals/{id}
```

## Params

| Parameter name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The pedal's unique record ID |

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
* [`Get all pedals`](get-all-pedals.md)
* [`Get songs by ID`](songs-get-songs-by-id.md)
