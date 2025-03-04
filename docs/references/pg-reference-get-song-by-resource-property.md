---
title: Get Song(s) by Non-SongID Resource Property
layout: default
parent: Songs Resource
nav_order: 5
---

# API Reference: Get Song(s) by Non-SongID Resource Property

Retrieve [`songs`](pg-resource-songs.md) in the database by resource properties other than song `id`.

## Endpoint

To retrieve song(s) based on a resource property other than song `id`, use either of the following endpoints:

* `GET /songs?{resource-property-name}={resource-property-value}` for requests using the full resource property value.
* `GET /songs?{resource-property-name}_like={resource-property-value}` for requests using a partial resource property value.

## Full Resource Property Value

See example below for retrieving song(s) where full resource property value is used.

**Request Example**

```shell
curl -X GET  http://localhost:3000/songs?artist=U2
```

**Return Body Example**

```shell
[
  {
    "id": 2,
    "name": "New Year's Day",
    "artist": "U2",
    "year": "1983",
    "label": "Island",
    "pedalIDs": [5,8]
  }
]
```

## Partial Resource Property Value

You can also retrieve song(s) using a partial match query. For example, searching by a keyword in the song name.

**Request Example**

```shell
curl -X GET  http://localhost:3000/songs?name_like=Day
```

**Return Body Example**

```shell
[
  {
    "id": 2,
    "name": "New Year's Day",
    "artist": "U2",
    "year": "1983",
    "label": "Island",
    "pedalIDs": [5,8]
  }
]
```

**Retrieving Song(s) by Single PedalID**

To retrieve song(s) by single pedal when multiple pedals are listed in the `pedalIDs` property, treat the request as a partial resource property value query.

*Request Example*

```shell
curl -X GET  http://localhost:3000/songs?pedalIDs_like=1
```

*Return Body Example*

```shell
[
  {
    "id": 3,
    "name": "That Lady, Pts. 1 & 2",
    "artist": "The Isley Brothers",
    "year": "1964",
    "label": "United Artists",
    "pedalIDs": [1,2]
  }
]
```

## Resource Properties

| Name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The ID of the song resource to which pedals are attached |
| `name` | string | The name of the song |
| `artist` | string | The name of the artist |
| `year` | number | The year the song was released |
| `label` | string | The label that published the song |
| `pedalIDs` | number | The pedal IDs attached to this particular song resource |

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

* [Songs](pg-resource-songs.md)
* [Update pedals](pg-reference-update-pedals.md)
* [Get pedal by ID](pg-reference-get-pedal-by-id.md)
