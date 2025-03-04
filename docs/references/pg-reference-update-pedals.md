---
title: Update Pedal
layout: default
parent: Pedals Resource
nav_order: 6
---

# API Reference: Update Pedal

Update an existing [`pedal`](pg-resource-pedals.md) in the database.

## Endpoint

To update an existing pedal in the database, use the `PATCH /pedals/{id}` endpoint.

## Request Example

```shell
curl -X PATCH  http://localhost:3000/pedals/1 \
 -H "Content-Type: application/json" \
 -d '{
   "family": "fuzz", 
  "songIDs": [3]
 }'
```

## Return Body Example

```shell
{
  "id": 1,
  "make": "Electro-Harmonix",
  "model": "Big Muff",
  "trim": "Ram's Head",
  "family": "fuzz",
  "songIDs": [3]
}
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

* [Pedals](pg-resource-pedals.md)
* [Update songs](pg-reference-update-songs.md)
* [Get pedal by ID](pg-reference-get-pedal-by-id.md)
