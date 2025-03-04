---
title: Get by Non-PedalID Resource Property
layout: default
parent: Pedals Resource
nav_order: 5
---

# API Reference: Retrieve Pedal(s) by Resource Property Other Than PedalID

Retrieve [`pedals`](pg-resource-pedals.md) in the database by resource properties other than pedal `id`.

## Endpoint

To retrieve pedals based on a resource property other than pedal `id`, use either of the following endpoints:

* `GET /songs?{resource-property-name}={resource-property-value}` for requests using the full resource property value.
* `GET /songs?{resource-property-name}_like={resource-property-value}` for requests using a partial resource property value.

## Full Resource Property Value

See example below for retrieving pedal(s) where full resource property value is used.

**Request Example**

```shell
curl -X GET  http://localhost:3000/pedals?make=Electro-Harmonix
```

**Return Body Example**

```shell
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
    "id": 5,
    "make": "Electro-Harmonix",
    "model": "Memory Man",
    "trim": "Deluxe",
    "family": "delay",
    "songIDs": [2]
  }
]
```

## Partial Resource Property Value

You can also retrieve pedal(s) using a partial match query. For example, searching by a keyword in the model name.

**Request Example**

```shell
curl -X GET  http://localhost:3000/pedals?model_like=Man
```

**Return Body Example**

```shell
[
  {
    "id": 5,
    "make": "Electro-Harmonix",
    "model": "Memory Man",
    "trim": "Deluxe",
    "family": "delay",
    "songIDs": [2]
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
* [`Updating songs`](pg-reference-updating-songs.md)
* [`Get pedal by ID`](pg-reference-get-pedal-by-id.md)

## Need Help?

We're here to help! For assistance, feel free to contact developer support at pedalgaragesupport@example.com.