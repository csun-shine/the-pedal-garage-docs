---
title: Add Song
layout: default
parent: Songs Resource
nav_order: 1
---

# API Reference: Add Song

Add a new [`song`](pg-resource-songs.md) to the database.

## Endpoint

To add a new song to the database, use the `POST /songs` endpoint.

## Request Example

```shell
curl -X POST http://localhost:3000/songs \
  -H "Content-Type: application/json" \
  -d '{
    "id": null,
    "name": "Barracuda",
    "artist": "Heart",
    "year": "1997",
    "label": "Portrait",
    "pedalIDs": [8,9]
  }'
```

*Notes*:

* To ensure the `id` field is placed at the beginning of the object and matches existing database entries, include it in your request. Otherwise, the `id` field will automatically be populated at the end of the object.
* Setting the `id` to null will trigger the system to generate a new, chronologically sequential identifier for the object.
* Nonapplicable fields may be left blank, or placeholder text such as "NA" may be used.


## Return Body Example

```shell
[
 {
  "id": 4,
  "name": "Barracuda",
  "artist": "Heart",
  "year": "1997",
  "label": "Portrait",
  "pedalIDs": [8,9],
 }
]
```

## Resource Properties

| Name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The ID of the song resource to which pedals are attached |
| `name` | string | The name of the song |
| `artist` | string | The name of the artist |
| `year` | number | The year the song was released |
| `label` | string | The label that published the song |
| `pedalIDs` | number | The pedal IDs attached to this particular song resource |

## Common Response Codes

| Status Code      | Category       | Description | Troubleshooting Tips |
|------------------|----------------|-------------|----------------------|
| 200 OK           | Success        | The request was successful. | Not Applicable |
| 201 Created      | Success        | A resource was successfully created. | Not Applicable |
| 204 No Content   | Success        | The request succeeded, but no content is returned. | Check the API documentation if content is expected. |
| 400 Bad Request  | Error   | The server could not understand the request. | Check for malformed syntax, invalid input, or missing fields in the request. |
| 404 Not Found    | Error   | The resource could not be found. | Confirm the URL is correct and the resource exists. |
| 500 Internal Server Error | Error | A generic error occurred on the server. | Start the service and try again. |
| ECONNREFUSED | Error | Service is offline. | Start the service and try again. |

## Related Topics

* [Songs](pg-resource-songs.md)
* [Add pedals](pg-reference-add-pedals.md)
* [Get song by ID](pg-reference-get-song-by-id.md)

## Need Help?

We're here to help! For assistance, feel free to contact developer support at pedalgaragesupport@example.com.