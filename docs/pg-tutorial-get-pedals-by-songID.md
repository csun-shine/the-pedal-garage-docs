---
layout: page
---

# Tutorial: Get Pedals by SongID

One of the core features of this API is the ability to retrieve a list of pedals associated with a songID.

This tutorial will walk you through the steps on how to get songs by pedal. You can use either curl via the command line or Postman.

Expect this tutorial to take 15 minutes to complete.

## Before you start

Make sure you have completed the "Before you start" tuturial and set up your development system prior to proceeding with this tutorial.

Having a basic understanding of how curl commands work and the Postman application functionality will be helpful.

## Running JSON server

1. There are a couple of different methods to open the Pedal Garage in a Git Bash window.

    Method 1: The first method is through the Git Hub desktop application. Make sure you are in the Pedal Garage repo, then click "Repository" in the navigation menu at the top. From the drop down menu, select "Open in Git Bash". This opens the main folder. Navigate to the api folder by running the `cd api` command.

    Method 2: Alternativley you can open the repo in Git Bash through the locally saved folder. Open whichever folder the Pedal Garage API is saved in. Select and right click the "api" sub-folder and select the "Open in Git Bash" option. This method automatically opens the api folder within Git Bash.

2. In the Git Bash window you have opened, run the JSON server by entering the following command.
   
```shell
json-server --watch the-pedal-garage-db-source.json
```

3. If you have successfully started the JSON server, the response should look like the following:

```shell
  \{^_^}/ hi!

  Loading pedal-garage-db-source.json
  Done

  Resources
  http://localhost:3000/pedals
  http://localhost:3000/songs

  Home
  http://localhost:3000

  Type s + enter at any time to create a snapshot of the database
  Watching...
```

## Get pedals by songID - curl

1. If you have not done so, run the JSON server following the steps given in the "Running JSON server" section.

2. Leave the JSON server running and open the repo again in another Git Bash window using one of the two methods explained in Step 1. For this, it does not matter which directory is opened.
   
3. Run the following curl command. Replace `{base_url}` with the base URL or directory where your API is hosted.

```shell
{base_url}/pedals?songIDs={songID}
```

4. For example, if we wanted to retrieve the pedals associated with songID 3:

```shell
{base_url}/pedals?songIDs=3
```

5. The response would look like:

```shell
[
  {
    "id": 1,
    "make": "Electro-Harmonix",
    "model": "Big Muff",
    "trim": "Ram's Head",
    "family": "fuzz",
    "songIDs": [
      3
    ]
  },
  {
    "id": 2,
    "make": "Maestro",
    "model": "PS-1A Phase Shifter",
    "trim": "",
    "family": "phaser",
    "songIDs": [
      3
    ]
  },
  {
    "id": 3,
    "make": "Dunlop",
    "model": "Cry Baby",
    "trim": "Classic",
    "family": "wah",
    "songIDs": [
      3
    ]
  }
]
```

6. Run the curl command given in Step 5 to retrieve the songs for whichver pedal you want.

## Get pedals by songID - Postman

1. If you have not done so, run the JSON server following the steps given in the "Running JSON server" section.

2. Leave the JSON server running and open the Postman application.

3. Either open a new request window or use whatever previous work environemtns and collections you have set up.

4. Select the "GET" method in the request box drop down menu.

5. In the request box, input the following. If you do not have an environemnt set up with a `{base_url}`, type out the base URL directly into the request box.

```shell
{{base_url}}/pedals 
```

6. Under the "Key" column of the "Query Params" section, input `songIDs`.

7. Under the "Value" column of the "Query Params" section, input the ID of whichever song you want to retrieve the pedals for. For example, put 3 if you want to retrieve the pedals for songID 3.

8. Click "Send".

9.  Response body should be populated with all pedals associated with songID 3 like below:

```shell
[
  {
    "id": 1,
    "make": "Electro-Harmonix",
    "model": "Big Muff",
    "trim": "Ram's Head",
    "family": "fuzz",
    "songIDs": [
      3
    ]
  },
  {
    "id": 2,
    "make": "Maestro",
    "model": "PS-1A Phase Shifter",
    "trim": "",
    "family": "phaser",
    "songIDs": [
      3
    ]
  },
  {
    "id": 3,
    "make": "Dunlop",
    "model": "Cry Baby",
    "trim": "Classic",
    "family": "wah",
    "songIDs": [
      3
    ]
  }
]
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

## Return status

| Status value | Return status | Description |
| ------------- | ----------- | ----------- |
| 200 | Success | Requested data returned successfully |
| 404 | Error | Specified task record not found |
|  ECONNREFUSED | N/A | Service is offline. Start the service and try again. |

## Related Topics

Congratulations! You've completed the "Get Pedals by SongID" tutorial. Explore other tutorials and related references below:

* [`Get Songs by PedalID`](tutorial-get-songs-by-pedalID.md)
* [`Songs`](pg-reference-songs.md)
* [`Pedals`](pg-reference-pedals.md)
