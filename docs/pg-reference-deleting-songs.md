---
layout: page
---

# API Reference

Deleting [`songs`](songs.md) from the database.

## URL

```shell
curl -X DELETE {base_url}/songs/{song_ID}
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

## Request Headers

None

## Request Body

None

## Return body

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

* [`Songs`](songs.md)
* [`Deleting pedals`](pg-reference-adding-pedals.md)
* [`Get song by ID`](pg-reference-get-song-by-id.md)
