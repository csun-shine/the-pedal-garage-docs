---
layout: page
---

# API Reference

Adding [`songs`](pg-resource-songs.md) to the database.

## URL

```shell
curl -XPOST {base_url}/songs
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

Content-Type: application/json

## Request Body Example

```js
{
"name": "Barracuda",
"artist": "Heart",
"year": "1997",
"label": "Portrait",
"pedalIDs": [8,9]
}
```

## Return Body Example

```js
{
  "name": "Barracuda",
  "artist": "Heart",
  "year": "1997",
  "label": "Portrait",
  "pedalIDs": [8,9],
  "id": 4
}
```

## Return Status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

* [`Songs`](pg-resource-songs.md)
* [`Add pedals`](pg-reference-add-pedals.md)
* [`Get song by ID`](pg-reference-get-song-by-id.md)
