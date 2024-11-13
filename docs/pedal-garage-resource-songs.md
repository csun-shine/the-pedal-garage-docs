---
layout: page
---

# `songs` resource

Base endpoint:

```shell

{base_url}/songs
```

Contains information about songs stored for the users of the Pedal Garage.

The Pedal Garage ships with existing database of songs. Users can also add songs - see [Add Songs](pedal-garage-add-songs.md) tutorial.

## Resource properties

Sample `pedals` resource

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

## READ

* [Match pedal to songs](pedal-garage-tutorial-match-pedal-to-songs.md)
* [Match song to pedals](pedal-garage-tutorial-match-song-to-pedals.md)
* [Add songs](pedal-garage-tutorial-add-songs.md)
