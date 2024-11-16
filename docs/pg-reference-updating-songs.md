---
layout: page
---

# API Reference

Updating [`songs`](songs.md) in the database.

## URL

```shell
{base_url}/songs
```

## Parameters

| Name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The ID of the song resource to which pedals are attached |
| `name` | string | The name of the song |
| `artist` | string | The name of the artist |
| `year` | number | The year the song was released |
| `label` | string | The label that published the song |
| `pedalIDs` | number | The pedal IDs attached to this particular song resource |

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
* [`Updating pedals`](pg-reference-updating-pedals.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)
