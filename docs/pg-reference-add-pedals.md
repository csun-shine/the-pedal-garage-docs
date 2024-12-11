---
layout: page
---

# API Reference: Add A New Pedal

Add a new [`pedal`](pg-resource-pedals.md) to the database.

## Endpoint

To add a new pedal to the databse, use the `POST /pedals` endpoint.

## Request Example

```shell
curl -X POST http://localhost:3000/pedals \
  -H "Content-Type: application/json" \
  -d '{
    "id": null,
    "make": "MXR", 
    "model": "M117R", 
    "trim": "NA", 
    "family": "flanger", 
    "songIDs": [4]
  }'
```

*Notes*:
* To ensure the `id` field is placed at the beginning of the object and matches existing database entries, include it in your request. Otherwise, the `id` field will automatically be populated at the end of the object. 
* Setting the `id` to null will trigger the system to generate a new, chronologically sequential identifier for the object.
* Nonapplicable fields may be left blank or placeholder text (i.e., NA) included.


## Return Body Example

```shell
[
  {
    "id": 9,
    "make": "MXR", 
    "model": "M117R", 
    "trim": "NA", 
    "family": "flanger", 
    "songIDs": [4]
  }
]
```

## Resource Properties

| Name | Type | Description |
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

## Related Topics

* [`Pedals`](pg-resource-pedals.md)
* [`Add songs`](pg-reference-add-songs.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)

## Need Help?

We're here to help! For assistance, feel free to contact developer support at pedalgaragesupport@example.com.