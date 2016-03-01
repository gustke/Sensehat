[![IMAGE ALT TEXT HERE](https://github.com/InitialState/wunderground-sensehat/wiki/img/Build Your Hyper Local Weather Dashboard.png)](https://youtu.be/H55_NNx4swQ)


![Sense HAT + Dashboard](https://github.com/InitialState/wunderground-sensehat/wiki/img/hyperlocal_dashboard.jpg)

The final step in this project is simply combining our Wunderground script and our Sense HAT script into a single Python script. We will be using https://github.com/InitialState/wunderground-sensehat/blob/master/sensehat_wunderground.py for this last step. Copy this file to your Pi or access it via the Github repository that we cloned earlier in this tutorial. Change into your wunderground-sensehat directory, and then nano into the sensehat_wunderground.py file by typing:

    $ nano sensehat_wunderground.py

Modify the user section near the top of the file:

```
# --------- User Settings ---------
STATE = "CA"
CITY = "San_Francisco"
SENSOR_LOCATION_NAME = "Office"
WUNDERGROUND_API_KEY = "PLACE YOUR WUNDERGROUND API KEY HERE"
BUCKET_NAME = ":partly_sunny: " + CITY + " Weather"
BUCKET_KEY = "shwu1"
ACCESS_KEY = "PLACE YOUR INITIAL STATE ACCESS KEY HERE"
MINUTES_BETWEEN_READS = 15
# ---------------------------------
```

Make sure you put your Wunderground API key, Initial State account access key, and desired city/state in this section. Specify the name of the location that your Sense HAT will be collecting environmental data in the SENSOR_LOCATION_NAME variable.  

Run the script on your Pi:
```
$ sudo python sensehat_wunderground.py
```

If you are ssh'ing into your Pi and want this script to run uninterrupted for a long time, run the script using the nohup (no hang-up) command:

```
$ nohup sudo python sensehat_wunderground.py &
```

After a couple of days, it is interesting to compare the temperature changes in your room versus the temperature changes outside. Same with humidity. If you want to add more sensors to the same dashboard, simply send the data to the same BUCKET_KEY specified in the User Settings (along with the same ACCESS_KEY). These additional sensors can be on any device and located anywhere and still send data to the same bucket. For example, you could have 10 different temperature sensors connected to 10 different types of single-board computers (Pi, Arduino, BeagleBone, Edison) and have them all streaming data into your one hyper-local weather dashboard.  

[<< Part 2: A Sense HAT Dashboard](Part-2.-A-Sense-HAT-Dashboard)