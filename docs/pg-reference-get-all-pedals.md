---
layout: page
---

# API Reference

Returns all [`pedals`](pedals.md) within the database.

## URL

```shell
{base_url}/pedals
```

## Request headers

Content-Type: application/json

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

## Return Parameters

| Name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The ID of the pedal resource to which songs are attached |
| `make` | string | The make of the pedal |
| `model` | string | The model of the pedal |
| `trim` | string | The trim of the pedal, if applicable |
| `family` | string | The family the pedal belongs to |
| `songIDs` | number | The song IDs attached to this particular pedal resource |

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

* [`Pedals`](pedals.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)
* [`Get song by ID`](pg-reference-get-song-by-id.md)
