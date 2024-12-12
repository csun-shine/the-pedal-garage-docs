---
layout: page
---

# Tutorial: Get Songs by PedalID

One of the core features of this API is the ability to retrieve a list of songs associated with a pedalID. This tutorial will walk you through the steps on how to get songs by pedal. You can use either curl via the command line or Postman. Expect this tutorial to take 15 minutes to complete.

## Before You Start

Make sure you have completed the "Before you start" tuturial and set up your development system prior to proceeding with this tutorial. Having a basic understanding of how curl commands work and the Postman application functionality will be helpful.

## Running JSON server

1. There are a couple of different methods to open the Pedal Garage in a Git Bash window.

   1.1. *Method 1*: The first method is through the Git Hub desktop application. Make sure you are in the Pedal Garage repo, then click "Repository" in the navigation menu at the top. From the drop down menu, select "Open in Git Bash". This opens the main folder. Navigate to the api folder by running the `cd api` command.

   1.2. *Method 2*: Alternativley you can open the repo in Git Bash through the locally saved folder. Open whichever folder the Pedal Garage API is saved in. Select and right click the "api" sub-folder and select the "Open in Git Bash" option. This method automatically opens the api folder within Git Bash.

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

## Get Songs by PedalID - curl

1. If you have not done so, run the JSON server following the steps given in the "Running JSON server" section.

2. Leave the JSON server running and open the repo again in another Git Bash window using one of the two methods explained in the "Running JSON Server" section. For this, it does not matter which directory is opened.

3. Run the following curl command. Replace `{base_url}` with the base URL or directory where your API is hosted.

   ```shell
   {base_url}/songs?pedalIDs={pedalID}
   ```

4. For example, if we wanted to retrieve the songs associated with pedalID 1:

   ```shell
   curl -X GET  {base_url}/songs?pedalIDs_like=1
   ```

5. The response would look like:

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

6. Run the curl command given in Step 3 to retrieve the songs for whichever pedal you want.

## Get Songs by PedalID - Postman

1. If you have not done so, run the JSON server following the steps given in the "Running JSON server" section.

2. Leave the JSON server running and open the Postman application.

3. Either open a new request window or use whatever previous work environemtns and collections you have set up.

4. Select the "GET" method in the request box drop down menu.

5. In the request box, input the following. If you do not have an environment set up with a `{base_url}`, type out the base URL directly into the request box.

   ```shell
   {{base_url}}/songs
   ```

6. Under the "Key" column of the "Query Params" section, input `pedalIDs_like`.

7. Under the "Value" column of the "Query Params" section, input the ID of whichever pedal you want to retrieve the songs for. For example, put `1` if you want to retrieve the songs for `pedalID: 1`.

8. Click "Send".

9. Response body should be populated with all songs associated with `pedalID: 1` like below:

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

10. Adjust the value in the "Value" column and send the request to retrieve the pedals for whichver song you want.

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

Congratulations! You've completed the "Get Pedals by SongID" tutorial. Explore other tutorials and related references below:

* [`Get Pedals by SongID`](tutorial-get-pedals-by-songID.md)
* [`Songs`](pg-reference-songs.md)
* [`Pedals`](pg-reference-pedals.md)

## Need Help?

We’re here to help! Feel free to contact developer support at pedalgaragesupport@example.com.
