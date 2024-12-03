---
layout: page
---

# Songs Resource

The `songs` resource represents the collection of songs available in The Pedal Garage API database. The Pedal Garage includes a pre-existing database of songs, which can be retrieved, added to, updated, or deleted through the API. This resource page provides an overview of the available endpoints for the `songs` resource, along with links to detailed reference pages for each operation. The resource page also includes explanations of resource properties and information on common response codes and error handling.

## Available Endpoints

* [Retrieve All Songs](pg-reference-get-all-songs.md): Fetch a complete list of songs in the databse.
* [Retrieve Songs by ID](pg-reference-get-song-by-id.md): Get detailed information about a specific song using its unique ID.
* [Add a New Song](pg-reference-add-songs.md): Add a new song to the database.
* [Update an Existing Song](pg-reference-updating-songs.md): Modify details of an exisiting song.
* [Delete a Song](pg-reference-deleting-songs.md): Remove a song from the database.

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

## Response Codes

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Error Handling
