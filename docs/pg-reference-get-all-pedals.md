---
layout: page
---

# API Reference

Returns all [`pedals`](pedals.md) within the database.

## URL

```shell
{base_url}/pedals
```

## Parameters

| Name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The ID of the pedal resource to which songs are attached |
| `make` | string | The make of the pedal |
| `model` | string | The model of the pedal |
| `trim` | string | The trim of the pedal, if applicable |
| `family` | string | The family the pedal belongs to |
| `songIDs` | number | The song IDs attached to this particular pedal resource |

## Request Headers

Content-Type: application/json

## Request Body Example

None

## Return Body Example

```js
[
      {
        "id": 1, 
        "make": "Electro-Harmonix",
        "model": "Big Muff",
        "trim": "Ram's Head",
        "family": "fuzz",
        "songIDs": [3]
      },
      {
        "id": 2, 
        "make": "Maestro",
        "model": "PS-1A Phase Shifter",
        "trim": "",
        "family": "phaser", 
        "songIDs": [3]
      },
      {
        "id": 3, 
        "make": "Dunlop",
        "model": "Cry Baby",
        "trim": "Classic",
        "family": "wah", 
        "songIDs": [3]
      }, 
      {
        "id": 4, 
        "make": "MXR",
        "model": "Dyna Comp Compressor",
        "trim": "",
        "family": "compressor", 
        "songIDs": []
      }, 
      {
        "id": 5, 
        "make": "Electro-Harmonix",
        "model": "Memory Man",
        "trim": "Deluxe",
        "family": "delay", 
        "songIDs": [2]
      }, 
      {
        "id": 6, 
        "make": "Boss",
        "model": "CE-2W",
        "trim": "Waza Craft",
        "family": "Chorus", 
        "songIDs": [1]
      }, 
      {
        "id": 7, 
        "make": "Boss",
        "model": "DM-2W",
        "trim": "Waza Craft",
        "family": "Delay", 
        "songIDs": [1]
      }, 
      {
        "id": 8, 
        "make": "Boss",
        "model": "Super Overdrive SD-1",
        "trim": "",
        "family": "overdrive", 
        "songIDs": [2]
      }
    ...
]
```

## Return Status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

* [`Pedals`](pedals.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)
* [`Get song by ID`](pg-reference-get-song-by-id.md)
