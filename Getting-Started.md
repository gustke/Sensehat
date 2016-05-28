# GitHub and Command Line Basics

[![IMAGE ALT TEXT HERE](https://github.com/InitialState/wunderground-sensehat/wiki/img/github commandline python basics.png)](https://youtu.be/w3muztSAJLU)

We’ve already put in a lot of the leg work for you putting the code together, and organizing the information. We’ll just need you to make a few adjustments along the way. 

To retrieve all of the things we’ve prepared for you, you’ll need to clone the repository from GitHub. Github is an awesome service that allows us to store, revise and manage projects like this.

To clone the repository all we need to do is go into our Pi’s terminal, or your computers terminal that’s SSH’d into your pi and type this command:


    $ git clone https://github.com/InitialState/wunderground-sensehat.git


Hit enter and you’ll see this information:


    pi@raspberrypi ~ $ git clone https://github.com/InitialState/wunderground-sensehat.git
    Cloning into 'wunderground-sensehat'...
    remote: Counting objects: 28, done.
    remote: Total 28 (delta 0), reused 0 (delta 0), pack-reused 28
    Unpacking objects: 100% (28/28), done.
    Checking connectivity... done.


Once you see this then congrats, you’ve successfully cloned the Github Repo and have all of the necessary files to build your Super Weather Station.

Before we move onto the next step, let’s take some time to explore around this directory and learn a few basic command line commands.

Type in the command below into your terminal:

     $ ls

This command lists everything that’s available in the directory that you’re currently in. This list shows that our Github Repo has been successfully cloned into our directory under the name “wunderground-sensehat.”

Let’s take a look at what’s in that directory.

To change directory’s, all you need to do is type “cd” and then type the name of the directory that you wish to go to. In this case, we’ll type

     $ cd wunderground-sensehat

Once we hit enter, you’ll see that we’re now in the wunderground-sensehat directory.

Let’s type ls again to see what files we’ve installed on our pi.

     README.md  sensehat.py  sensehat_wunderground.py  wunderground.py

Here we see the we’ve got our readme document, and a couple different python files. Let’s take a look at sensehat.py. Instead of jumping into the file w/ the cd command like we did for directory’s, we’re going to use the nano command. The nano command allows us to open up the nano text editor where we have all of our python code for each segment of this project.

Go ahead and type

     $ nano sensehat.py
 

Here you can see all of the code we’ve prepared for you for this project. We’re not going to make any changes to this document just yet, but feel free to scroll around and see what we’re going to be doing later in this tutorial.

[<< Introduction](home) - [Part 1: Wunderground >>](Part-1.-Wunderground)