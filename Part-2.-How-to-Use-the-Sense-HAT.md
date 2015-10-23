The first step in using the Sense HAT is to physically install it onto your Pi. With the Pi powered down, attached the HAT as shown below.

![Sense HAT + Dashboard](https://github.com/InitialState/wunderground-sensehat/wiki/img/sensehat_install.png)

Power on your Pi. We need to install the Python library to make it easy to read the sensor values from the Sense HAT. First, you will need to ensure that everything is up-to-date on your version of Raspbian:

```
$ sudo apt-get update
```

Next, install the Sense HAT Python library:

```
$ sudo apt-get install sense-hat
```

Reboot your Pi. We are ready to test the Sense HAT by reading sensor data from it and sending that data to Initial State.

[<< Part 2: Sense HAT](Part-2.-Sense-HAT) - [Part 2: A Sense HAT Dashboard >>](Part-2.-A-Sense-HAT-Dashboard)