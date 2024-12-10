---
layout: page
---

# Quick Start Guide

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
curl -GET http://localhost:3000/pedals/1
```

**Return Example**

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

## Add a Pedal

**Endpoint**

To add a pedal to the database, use the `POST /pedals` endpoint.

**Request Example**

```shell
curl -XPOST http://localhost:3000/pedals \
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
curl -GET http://localhost:3000/songs?pedalIDs_like=1
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

## Error Handling

Some common situations that cause errors include:

1. Mistyping a command.
2. Being in the incorrect directory.
3. A required software component didn't install correctly.
4. A required software component isn't up to date.

## Next Steps

 Congratulations on completing the Quick Start Guide! Below are links to tutorials for some key features of the API as well as the API Reference page. Happy coding!

* [Get Pedals by SongID](pg-tutorial-get-pedals-by-songID.md)
* [Get Songs by PedalID](pg-tutorial-get-songs-by-pedalID.md)
* [API Reference](API-reference.md)

## Need Help?

We’re here to help! Feel free to contact developer support at pedalgaragesupport@example.com.