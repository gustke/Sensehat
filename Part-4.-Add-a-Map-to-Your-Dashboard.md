![Dashboard with Map](https://github.com/InitialState/wunderground-sensehat/wiki/img/DashboardWithMap.jpg)
We can easily add a map tile to our dashboard showing the location of our weather stream. You can learn more about the interactive map view in tiles at http://support.initialstate.com/knowledgebase/articles/800232-tiles-map-view. We could simply add a new streamer.log statement in our Python script (and I'll explain how you can do that at the end of this section). Instead, we will take this opportunity to show you a different way to send data into your dashboard.

### Step 1: Get your Location's Latitude/Longitude Coordinates
![Step 1: Get Coordinates](https://github.com/InitialState/wunderground-sensehat/wiki/img/GetCoordinates.jpg)
You need to get the latitude/longitude coordinates of your location. One way to do this is to go to Google Maps, search for your location, and zoom in to your exact location. In the URL, you will see your latitude/longitude coordinates. In the example above, my coordinates are 35.925298,-86.8679478. Copy your coordinates (you will need them in step 2). 

### Step 2: Build a URL to Send Data Into Your Dashboard
![Step 2: Get API Endpoint](https://github.com/InitialState/wunderground-sensehat/wiki/img/AddMapStep1.jpg)
Click on the "settings" link under the bucket name in the bucket shelf.  This will bring up the screen above.  Copy the text in the API Endpoint section and paste it in your favorite text editor.  We will use this to build a URL that we can use to send data into our existing bucket and dashboard.

In my bucket, the text that I copied looks like:
https://groker-dev.initialstate.com/api/events?accessKey=bqHk4F0Jj4j4M4CrhJxEWv6ck3nfZ79o&bucketKey=shwu1

Your URL will have your accessKey and bucketKey. We need to add a stream name and value to the URL parameters to complete the URL. Add "&MapLocation=YOUR_COORDINATES_FROM_STEP1" to your URL (insert the coordinates from Step 1, no spaces and don't copy mine!!):
https://groker-dev.initialstate.com/api/events?accessKey=bqHk4F0Jj4j4M4CrhJxEWv6ck3nfZ79o&bucketKey=shwu1&MapLocation=35.925298,-86.8679478

Paste your complete URL to the address bar of your browser and hit enter (or use the 'curl' command at a command prompt) to send your map coordinates to the stream, "MapLocation", in your new bucket.

![Map Tile](https://github.com/InitialState/wunderground-sensehat/wiki/img/MapTile.jpg)

If you look at your dashboard in Tiles now (you may have to refresh if you get impatient), a new Tile named MapLocation should have appeared zoomed into your current location.

### Step 2 Alternative: Modify Your Script
If you really do not like Step 2 above, you can simply add another streamer.log statement to your Python script. Simply add the line

```
streamer.log("MapLocation","YOUR_COORDINATES_FROM_STEP1")
```

somewhere inside the def main(): function of the sensehat_wunderground.py script (pay attention to indentation b/c Python requires you to follow strict indentation rules). For example, I added 

```
streamer.log("MapLocation","35.925298,-86.8679478")
```

right after line 138.

[<< Part 3: Hyper-Local Weather Dashboard](Part-3.-Hyper-Local-Weather-Dashboard) - [Part 5: (Bonus) Configure Your Own Weather Alerts >>](Part-5.-Configure-Your-Own-Weather-Alerts)