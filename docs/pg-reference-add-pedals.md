---
layout: page
---

# API Reference

Adding [`pedals`](pg-resource-pedals.md) to the database.

## URL

```shell
curl -XPOST {base_url}/pedals
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

Content-Type: application/json

## Request Body Example

```js
{
  "make": "MXR", 
  "model": "M117R", 
  "trim": "", 
  "family": "flanger", 
  "songIDs": [4]
}
```

## Return Body Example

```js
{
  "make": "MXR",
  "model": "M117R",
  "trim": "",
  "family": "flanger",
  "songIDs": [4],
  "id": 9
}
```

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

* [`Pedals`](pg-resource-pedals.md)
* [`Add songs`](pg-reference-add-songs.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)
