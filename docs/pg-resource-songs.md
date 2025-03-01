---
layout: page
---

# Songs Resource

The `songs` resource represents the collection of songs available in The Pedal Garage API database. The Pedal Garage includes a pre-existing database of songs, which can be retrieved, added to, updated, or deleted through the API. This resource page provides an overview of the available endpoints for the `songs` resource, along with links to detailed reference pages for each operation. The resource page also includes explanations of resource properties and information on common response codes and error handling.

## Resource Options

* [Retrieve All Songs](pg-reference-get-all-songs.md): Fetch a complete list of songs in the database.
* [Retrieve Songs by ID](pg-reference-get-song-by-id.md): Get detailed information about a specific song using its unique ID.
* [Add a New Song](pg-reference-add-songs.md): Add a new song to the database.
* [Update an Existing Song](pg-reference-updating-songs.md): Modify details of an existing song.
* [Delete a Song](pg-reference-deleting-songs.md): Remove a song from the database.
* [Retrieve Song(s) by Resource Property Other Than SongID](pg-reference-get-song-by-resource-property.md): Get detailed information about a specific pedal using properties other than SongID.

## Resource Properties

Example `songs` resource

```js

    {
        "id": 1, 
        "name": "Just Like Heaven",
        "artist": "The Cure",
        "year": 1987,
        "label": "Fiction", 
        "pedalIDs": [6,7]
    }
```

| Property name | Type | Description |
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
