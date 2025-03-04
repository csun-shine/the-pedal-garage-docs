---
title: Delete Song
layout: default
parent: Songs Resource
nav_order: 2
---

# API Reference: Delete a Song

Delete a [`song`](pg-resource-songs.md) from the database.

## Endpoint

To delete a song from the database, use the `DELETE /songs/{id}` endpoint.

## Request Example

```shell
curl -X DELETE http://localhost:3000/songs/4
```

## Return Body Example

```shell
{}
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

* [`Songs`](pg-resource-songs.md)
* [`Deleting pedals`](pg-reference-deleting-pedals.md)
* [`Get song by ID`](pg-reference-get-song-by-id.md)

## Need Help?

We're here to help! For assistance, feel free to contact developer support at pedalgaragesupport@example.com.
