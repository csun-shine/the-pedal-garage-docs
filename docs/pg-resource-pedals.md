---
layout: page
---

# Pedals Resource

The `pedals` resource represents the collection of pedals available in The Pedal Garage API database. The Pedal Garage includes a pre-existing database of pedals, which can be retrieved, added to, updated, or deleted through the API. This resource page provides an overview of the available endpoints for the `pedals` resource, along with links to detailed reference pages for each operation. The resource page also includes explanations of resource properties and information on common response codes and error handling.

## Available Endpoints

* [Retrieve All Pedals](pg-reference-get-all-pedals.md): Fetch a complete list of all pedals in the databse.
* [Retrieve Pedals by ID](pg-reference-get-pedal-by-id.md): Get detailed information about a specific pedal using its unique ID.
* [Add a New Pedal](pg-reference-add-pedals.md): Add a new pedal to the database.
* [Update an Existing Pedal](pg-reference-updating-pedals.md): Modify details of an exisiting pedal.
* [Delete a Pedal](pg-reference-deleting-pedals.md): Remove a pedal from the database.

## Resource Properties

Example `pedals` resource

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

## Response Codes

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Error Handling
