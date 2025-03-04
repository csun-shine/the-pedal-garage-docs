---
title: Quickstart Guide
layout: default
nav_order: 3
---

# Quickstart Guide

Ready to dive in? This guide will walk you through the steps of making your first requests with The Pedal Garage API!

## Before You Begin

If you have not done so already, make sure to have your development environment set up prior to following this guide. Refer to the [Before You Start](pg-before-you-start.md) guide.

Having a basic understanding of how curl commands work and the Postman application functionality will be helpful.

Expect this guide to take about 15 minutes to complete.

## Retrieve a Specific Pedal by ID

**Endpoint**

To retrieve details about a specific pedal, use the `GET /pedals/{id}` endpoint.

**Request Example**

```shell
curl -X GET http://localhost:3000/pedals/1
```

**Return Example**

```shell
[
  {
    "id": 1, 
    "make": "Electro-Harmonix",
    "model": "Big Muff",
    "trim": "Ram's Head",
    "family": "fuzz",
    "songIDs": [3]
  }
]
```

## Add a Pedal

**Endpoint**

To add a pedal to the database, use the `POST /pedals` endpoint.

**Request Example**

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

*Note*: To ensure the `id` field is placed at the beginning of the object and matches existing database entries, include
it in your request. Otherwise the `id` field will automatically be populated at the end of the object. Setting the id
to null will trigger the system to generate a new, chronologically sequential identifier for the object.

**Return Example**

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

## Search for Songs by Pedal

**Endpoint**

To search for songs by pedal, use the `GET /songs?pedalIDs_like={pedalID}` endpoint.

**Request Example**

```shell
curl -X GET http://localhost:3000/songs?pedalIDs_like=1
```

**Return Example**

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

## Troubleshooting

**Common Causes of Errors**

Some common situations that cause errors include:

* **Incorrect Command**: Double-check your commands for typos or errors.
* **Wrong Directory**: Verify that you are in the correct directory in your command-line tool.
* **Missing Software**: Ensure that all required software components are installed correctly, as outlined in the [Before You Start](pg-before-you-start.md) guide.
* **Outdated Software**: Refer to the [Before You Start](pg-before-you-start.md) guide for instructions on updating your software to the latest version.

**Common Response Codes**

| Status Code      | Category       | Description | Troubleshooting Tips |
|------------------|----------------|-------------|----------------------|
| 200 OK           | Success        | The request was successful. | Not Applicable |
| 201 Created      | Success        | A resource was successfully created. | Not Applicable |
| 204 No Content   | Success        | The request succeeded, but no content is returned. | Check the API documentation if content is expected. |
| 400 Bad Request  | Error   | The server could not understand the request. | Check for malformed syntax, invalid input, or missing fields in the request. |
| 404 Not Found    | Error   | The resource could not be found. | Confirm the URL is correct and the resource exists. |
| 500 Internal Server Error | Error | A generic error occurred on the server. | Start the service and try again. |
| ECONNREFUSED | Error | Service is offline. | Start the service and try again. |

## Next Steps

 Congratulations on completing the Quick Start Guide! Here are links to tutorials for the API's key features and reference page to help you continue your Pedal Garage journey. Happy coding!

* [Get Pedals by SongID](pg-tutorial-get-pedals-by-songID.md)
* [Get Songs by PedalID](pg-tutorial-get-songs-by-pedalID.md)
* [API Reference](API-reference.md)

## Need Help?

We’re here to help! Feel free to contact developer support at pedalgaragesupport@example.com.