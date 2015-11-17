We want to stream all of our weather data to a cloud service and have that service turn our data into a nice dashboard that we can access from our laptop or mobile device. Our data needs a destination. We will use Initial State as that destination.

###Step 1: Register for Initial State Account
Go to [https://www.initialstate.com/app#/register/](https://www.initialstate.com/app#/register/) and create a new account.

###Step 2: Install the ISStreamer
Install the Initial State Python module onto your Raspberry Pi:

At a command prompt (don’t forget to SSH into your Pi first), run the following command:

```
$ cd /home/pi/
$ \curl -sSL https://get.initialstate.com/python -o - | sudo bash
```

> **Security Note**: The above command has some important anatomy that the user should be aware of. 1) There is a preceding `\` before `curl`. This is important to ensure no alias of `curl` gets run if one was created. This helps mitigate risk of the command doing more than intended. 2) The command is a piped command, so when running, you are piping the output of a script that is being retrieved from `https://get.initialstate.com/python` into the command `sudo bash`. This is done to simplify installation, however, it should be noted that `https` is important here for helping ensure no man-in-the-middle manipulation of the install script, especially since the script is being run with elevated privileges. This is a common way to simplify install and setup, but if you are a little more wary there are some slightly less convenient alternatives: you can break the command out into two steps and investigate the bash script being downloaded from the curl command yourself to insure it's fidelity OR you can [follow the pip instructions](https://github.com/InitialState/python_appender#using-package-management), you just wont get an automatically generated example script.

###Step 3: Make some Automagic

After Step 2 you will see something similar to the following output to the screen:

```
pi@raspberrypi ~ $ \curl -sSL https://get.initialstate.com/python -o - | sudo bash
Password:
Beginning ISStreamer Python Easy Installation!
This may take a couple minutes to install, grab some coffee :)
But don't forget to come back, I'll have questions later!

Found easy_install: setuptools 1.1.6
Found pip: pip 1.5.6 from /Library/Python/2.7/site-packages/pip-1.5.6- py2.7.egg (python 2.7)
pip major version: 1
pip minor version: 5
ISStreamer found, updating...
Requirement already up-to-date: ISStreamer in /Library/Python/2.7/site-packages
Cleaning up...
Do you want automagically get an example script? [y/N]
```

_(the output may be different and take longer if you have never installed the Initial State Python streaming module before)_

When prompted to automatically get an example script, type y. This will create a test script that we can run to ensure that we can stream data to Initial State from our Pi. You will be prompted:

```
Where do you want to save the example? [default: ./is_example.py]: 
```

You can either type a custom local path or hit enter to accept the default.

You will be prompted for your username and password that you just created when you registered your Initial State account. Enter both and the installation will complete.

###Step 4: Access Keys
Let’s take a look at the example script that was created.



```
$ nano is_example.py
```

On line 15, you will see a line that starts with `streamer = Streamer(bucket_ ...`. This lines creates a new data bucket named “Python Stream Example” and is associated with your account. This association happens because of the `access_key=”...”` parameter on that same line. That long series of letters and numbers is your Initial State account access key. If you go to your Initial State account in your web browser, click on your username in the top right, then go to “my account”, you will find that same access key at the bottom of the page under “Streaming Access Keys”.

![Access Keys](https://github.com/InitialState/beerfridge/wiki/img/access-keys.png)

Every time you create a data stream, that access key will direct that data stream to your account (so don’t share your key with anyone).

###Step 5: Run the Example
Run the test script to make sure we can create a data stream to your Initial State account. Run the following:

```
$ python is_example.py
```

###Step 6: Profit
Go back to your Initial State account in your web browser. A new data bucket called “Python Stream Example” should have shown up on the left in your log shelf (you may have to refresh the page). Click on this bucket and then click on the Waves icon to view the test data.

![Example Stream Screenshot](https://github.com/InitialState/beerfridge/wiki/img/example-stream.png)

You will want to step through the Waves tutorial to familiarize yourself with how to use this data visualization tool. Next, view the data in Tiles to see this same data in dashboard form. 

![Example Stream Screenshot](https://github.com/InitialState/beerfridge/wiki/img/example-stream-tiles.png)

You are now ready to initialize and run the NodeJS server!

[<< Part 1: Install the NodeJS Server](Part-1.-Install-the-NodeJS-Server) - [Part 1: Initialize & Run the Server >>](Part-1.-Initialize-&-Run-the-Server)