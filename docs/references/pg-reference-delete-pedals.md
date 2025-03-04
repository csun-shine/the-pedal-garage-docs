---
title: Delete Pedal
layout: default
parent: Pedals Resource
nav_order: 2
---

# API Reference: Delete a Pedal

Delete a [`pedal`](pg-resource-pedals.md) from the database.

## Endpoint

To delete a pedal from the database, use the `DELETE /pedals/{id}` endpoint.

## Request Example

```shell
curl -X DELETE http://localhost:3000/pedals/9
```

## Return Body Example

```shell
{}
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
* [Delete songs](pg-reference-delete-songs.md)
* [Get pedal by ID](pg-reference-get-pedal-by-id.md)

## Need Help?

We're here to help! For assistance, feel free to contact developer support at pedalgaragesupport@example.com.