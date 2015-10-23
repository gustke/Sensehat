Now for the fun part. We are ready to start using the Wunderground API to create a weather dashboard and capture the weather history for wherever we choose.  To do this, we are going to use the Python script:
https://github.com/InitialState/wunderground-sensehat/blob/master/wunderground.py

Copy this script to your Pi. Before you run it, you need to set your desired parameters and insert your keys. Edit the section near the top of the script:

```
# --------- User Settings ---------
STATE = "CA"
CITY = "San_Francisco"
WUNDERGROUND_API_KEY = "PLACE YOUR WUNDERGROUND API KEY HERE"
BUCKET_NAME = ":partly_sunny: " + CITY + " Weather"
BUCKET_KEY = "wu1"
ACCESS_KEY = "PLACE YOUR INITIAL STATE ACCESS KEY HERE"
MINUTES_BETWEEN_READS = 15
# ---------------------------------
```

You need to set the desired state and city. You also have to insert your Wunderground API key and your Initial State account access key or your data isn't going to go anywhere. The MINUTES_BETWEEN_READS parameter will set how often your script will poll the Wunderground API for weather information. 15 minutes provides a nice interval.

Once you have your parameters set, you are ready to run your script:

```
$ sudo python wunderground.py
```

This script is going to do a bit more than just read the weather data and send it to Initial State. This script is going to take advantage of the emoji support built into Initial State's tools to make the dashboard a bit more sexy. You can see the logic used to take the weather status from the current_observation -> icon status and convert it to an emoji token in the weather_icon function. 



[<< Part 1: Initial State](Part-1.-Initial-State) - [Part 2: Sense HAT >>](Part-2.-Sense-HAT)