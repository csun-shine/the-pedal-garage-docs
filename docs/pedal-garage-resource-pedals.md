---
layout: page
---

# `pedals` resource

Base endpoint:

```shell

{base_url}/pedals
```

Contains information about pedals stored for the users of the Pedal Garage.

The Pedal Garage ships with existing database of pedals. Users can also add pedals - see [Add Pedals](pedal-garage-add-pedals.md) tutorial.

## Resource properties

Sample `pedals` resource

```js

    {
        "id": 1, 
        "make": "Electro-Harmonix",
        "model": "Big Muff",
        "trim": "Ram's Head",
        "family": "fuzz",
        "songIDs": [3]
    }
```

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The ID of the pedal resource to which songs are attached |
| `make` | string | The make of the pedal |
| `model` | string | The model of the pedal |
| `trim` | string | The trim of the pedal, if applicable |
| `family` | string | The family the pedal belongs to |
| `songIDs` | number | The song IDs attached to this particular pedal resource |

## READ

* [Match pedal to songs](pedal-garage-tutorial-match-pedal-to-songs.md)
* [Match song to pedals](pedal-garage-tutorial-match-song-to-pedals.md)
* [Add pedals](pedal-garage-tutorial-add-pedals.md)
