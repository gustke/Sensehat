![Sense HAT + Dashboard](https://github.com/InitialState/wunderground-sensehat/wiki/img/sensehat_install.png)

The first step in using the Sense HAT is to physically install it onto your Pi. With the Pi powered down, attached the HAT as shown above.  Power on your Pi. 

Now we need to install the Python library to make it easy to read the sensor values from the Sense HAT. First, you will need to ensure that everything is up-to-date on your version of Raspbian:

```
$ sudo apt-get update
```

Next, install the Sense HAT Python library:

```
$ sudo apt-get install sense-hat
```

Reboot your Pi.

Let's test our Sense HAT to make sure everything is working. We will use the script located at https://github.com/InitialState/wunderground-sensehat/blob/master/sensehat.py. Copy this script to a file on your Pi. Notice on the first line that we are importing the SenseHat library into the script. Before you run this script, we need to setup our user parameters. 

```
# --------- User Settings ---------
CITY = "Nashville"
BUCKET_NAME = ":partly_sunny: " + CITY + " Weather"
BUCKET_KEY = "sensehat"
ACCESS_KEY = "Your_Access_Key"
SENSOR_LOCATION_NAME = "Office"
MINUTES_BETWEEN_SENSEHAT_READS = 0.1
# ---------------------------------
```

Specifically, you need to set your ACCESS_KEY to your Initial State account access key. 

[<< Part 2: Sense HAT](Part-2.-Sense-HAT) - [Part 2: A Sense HAT Dashboard >>](Part-2.-A-Sense-HAT-Dashboard)