---
layout: page
---

# API Reference

Deleting [`pedals`](pedals.md) from the database.

## URL

```shell
curl -X DELETE {base_url}/pedals/{pedal_ID}
```

## Parameters

| Name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The ID of the pedal resource to which songs are attached |
| `make` | string | The make of the pedal |
| `model` | string | The model of the pedal |
| `trim` | string | The trim of the pedal, if applicable |
| `family` | string | The family the pedal belongs to |
| `songIDs` | number | The song IDs attached to this particular pedal resource |

## Request Headers

None

## Request Body Example

None

## Return Body Example

```js
{}
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

* [`Pedals`](pedals.md)
* [`Deleting songs`](pg-reference-deleting-songs.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)
