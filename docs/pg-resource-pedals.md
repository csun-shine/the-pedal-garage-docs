---
layout: page
---

# Pedals Resource

The `pedals` resource represents the collection of pedals available in The Pedal Garage API database. The Pedal Garage includes a pre-existing database of pedals, which can be retrieved, added to, updated, or deleted through the API. This resource page provides an overview of the available endpoints for the `pedals` resource, along with links to detailed reference pages for each operation. The resource page also includes explanations of resource properties and information on common response codes and error handling.

## Resource Options

* [Retrieve All Pedals](pg-reference-get-all-pedals.md): Fetch a complete list of all pedals in the database.
* [Retrieve Pedals by ID](pg-reference-get-pedal-by-id.md): Get detailed information about a specific pedal using its unique ID.
* [Add a New Pedal](pg-reference-add-pedals.md): Add a new pedal to the database.
* [Update an Existing Pedal](pg-reference-updating-pedals.md): Modify details of an existing pedal.
* [Delete a Pedal](pg-reference-deleting-pedals.md): Remove a pedal from the database.
* [Retrieve Pedal(s) by Resource Property Other Than PedalID](pg-reference-get-pedal-by-resource-property.md): Get detailed information about a specific pedal using properties other than PedalID.

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

