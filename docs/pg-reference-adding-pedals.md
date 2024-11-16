---
layout: page
---

# API Reference

Adding [`pedals`](pedals.md) to the database.

## URL

```shell
{base_url}/pedals
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

## Request headers

Content-Type: application/json

## Request body

```js
[input]
```

## Return body

```js
[input]
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

* [`Pedals`](pedals.md)
* [`Adding songs`](pg-reference-adding-songs.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)
