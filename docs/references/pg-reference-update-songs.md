---
title: Update Song
layout: default
parent: Songs Resource
nav_order: 6
---

# API Reference: Update an Existing Song

Update a [`song`](pg-resource-songs.md) in the database.

## Endpoint

To update an existing song in the database, use the `PATCH /songs/{id}` endpoint.

## Request Body Example

```shell
curl -X PATCH  http://localhost:3000/songs/1 \
 -H "Content-Type: application/json" \
 -d '{
   "year": "1987", 
   "pedalIDs": [6,7]
 }'
```

## Return Body Example

```shell
[
 {
  "id": 1,
  "name": "Just Like Heaven",
  "artist": "The Cure",
  "year": "1987",
  "label": "Fiction",
  "pedalIDs": [6,7]
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
* [Update pedals](pg-reference-update-pedals.md)
* [Get pedal by ID](pg-reference-get-pedal-by-id.md)

## Need Help?

We're here to help! For assistance, feel free to contact developer support at pedalgaragesupport@example.com.