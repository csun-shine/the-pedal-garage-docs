---
layout: page
---

# API Reference

Returns a [`pedal`](pedals.md) array that contains only the pedal resource specified by the `id` parameter, if it exists.

## URL

```shell
{base_url}/pedals/{id}
```

## Parameters

| Parameter name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The pedal's unique record ID |

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
* [`Get all pedals`](pg-reference-get-all-pedals.md)
* [`Get songs by ID`](pg-reference-get-songs-by-id.md)
