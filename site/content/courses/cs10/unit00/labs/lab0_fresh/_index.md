---
title: "0. Freshly Baked Pi"
type: lab
---

# Raspbery Pi 🥧
This year, you'll be using Raspberry Pi's as our computational companions. Before you get too excited, these
are not warm, flakey baked goods, these are tiny computers built entirely on a single circuit board.

But even if these Pi's might not be as tasty as edible raspberry pies, they are still pretty exciting!

## Why Pi?
Raspberry Pi's are tiny but powerful computers that can be used for tons of DIY projects. Since Raspberry
Pi's are so small but have full computational, networking, and hardware capabilities, they are great tools
for making robots, internet of things devices, networking services, and much more.

{{< look-action >}} Check out some of the projects you can make with Raspberry Pi's:

{{< youtube "ZXpGNBzHKRY" >}}

## Uboxing

**You will be using your Pi all year, so you've got to take good care of it! Treat it like you would treat
a newborn baby if it were a computer you were building.**

## Setup
Now that you've got a sense of the layout of your Pi, let's get setup so you can start coding with it.

{{< aside >}}
Before you run the setup script, make sure you know the name and password of your home wifi network.
If you know that your wifi network has special settings, talk to a teacher before beginning the setup.

**Currently, the setup script does not work if your wifi network's password contains a space. If this is the case,
please tell {{< teacher >}} before starting the setup.**
{{< /aside >}}

0. Take the USB to MicroUSB cable and plug your Pi in. You can plug it into your computer or into a power
outlet with a USB power plug. The red and green light on the side of your Pi should turn on and flash once
it is powered.
0. Give your Pi a minute or two to boot up. Once it has booted, it will begin broadcasting a wifi signal called
`RPiHotspotN` where `N` is the number on your Pi.
    - If you don't see the Pi's network. Try reboot your Pi by unplugging it and pluggin it back in.
    - If you still don't see the network, try manually adding the network on your computer using "Join other network..."
    and entering the Pi's network name (`RPiHotspotN`), selecting "WPA/WPA2 Personal" for the security setting, and
    entering the password `cs10_setup`.
0. Connect your computer to this wifi network using the password `cs10_setup`. *Note: This wifi network will not
have access to the internet. You will have to temporarily leave the Google Meet. If you have a problem during setup,
you will need to reconnect to your regular wifi network and rejoin the Google Meet.*
0. Once you are connected to the Pi's wifi network, open a Terminal window on your computer.
0. Type the following into your terminal window: `ssh setup@192.168.50.5`
0. When prompted for a password, enter `setup`. Once this command runs, you will be remotely controlling the Pi
through the wifi network it is broadcasting!
0. The Pi will automatically run a setup script. Choose option 0.
0. Follow the instructions in the script to setup up a new user. *Note: your username must not contain any spaces. Only
the first word you enter will be used.*
0. Follow the instructions to add your home wifi network into the Pi's network settings.
0. After you finish the setup script, your Pi will reboot and your remote connection will be closed.
0. Reconnect your computer to your regular wifi network and rejoin the Google Meet.

## Using Pi
Your Pi should now be connected to your home wifi network. Now you can connect to it remotely with your computer and 
it will have access to the internet!

### Connecting to your Pi (SSH)
Once your Pi is connected to your home wifi network, you can remotely connect to it with your computer through your wifi router.
Tp understand how this works, you'll need to understand some basics of networking.

{{< tabs networking >}}

{{< tab "Text Eplanation" >}}
You are probably most familiar with your wifi router because it offers your computer access to the internet. In this case, your
computer connects to the router's wifi network and begins sending messages to the router. The wifi router recieves these messages
and forwards them to the appropriate place via the internet. For example, if you click [this link](https://en.wikipedia.org/wiki/ARPANET),
your computer will send a request to your wifi router to return the content of the page at the URL. Your router will recieve this
message and forwards it to one of Wikipedia's servers somewhere in the world. When the Wikipedia servver recieves the message, it
reads it, packages up the content of the page at the URL, and sends the content back to your router. Your router then forwards this
reply to your computer which interprets the content and displays it in your web browser.

{{< figure src="images/courses/cs10/unit00/00_fresh_internet.png" width="100%" title="Connecting to the internet via wifi" >}}

This is obviously an extremely useful feature of your wifi router. You probably use it every day! However, we're going to use another
feature of your wifi router that you may not have used before.

Generally, wifi routers also create local area networks (LAN) that create a wireless interface between all the devices connected to
the router. For example, if you have a wifi-enabled speaker or printer, your wifi router is probably making the connection between
your computer (or phone) and the device. When you want to print something, your computer sends a message to your wifi router containing
the file it wants to print. However, rather than being addressed to a destination at a server somewhere far away, this message is addressed
to your printer. Your wifi router notices this and forwards the message to your printer through the LAN. When the printer recieves
the message, it interprets it and prints the file. Your communication never left the local network created by your wifi router.

{{< figure src="images/courses/cs10/unit00/00_fresh_lan.png" width="100%" title="Connecting to another deivce over a LAN" >}}
{{< /tab >}}

{{< tab "Video Explanation" >}}

{{< youtube id="7_LPdttKXPc" autoplay="true" >}}

{{< /tab >}}
{{< /tabs >}}

Since both your Pi and your home computer are connected to your home wifi network, you
can connect to your Pi using your computer using a Secure Shell (SSH) connection.

{{< code-action >}} Follow the steps below to connect to your Pi:

0. Make sure your computer is connected to your home wifi network
0. In a terminal window, run the command `arp -a`. This will list all the devices
on your home wifi network.
0. Look for the device labeled `rapberrypi`. Record the set of numbers in parentheses
following the name. It should look something like this: `192.167.1.500`. This is the IP address
of your Pi, basically it's unique identifier.
0. Run the command `ssh USER@IP.ADDRESS`, replacing `USER` with the username you created
in the setup and `IP.ADDRESS` with the IP address you recorded from the last step. It should
look something like this: `ssh sifyi@192.167.1.500`.
0. Enter the user password you used during the setup when prompted for a password.
0. You should now be remotely connected to your Pi!

{{< aside >}}
If you cannot find a `raspberrypi` device on your wifi network, wait a couple minutes
to allow the Pi to reboot and connect to the internet. Try running the `arp -a` command a couple times.
If the problem persists, you may need to re-enter your wifi password. You can do this by reconnecting
to the `RPiHotspotN` wifi network, running `ssh setup@192.168.50.5` (password "setup"), choosing 
option 2 from the setup, and reentering your wifi credentials.

**If you are able to connect to your Pi's wifi hotspot, it has not been able to connect to a wifi network
and you'll need to re-enter the wifi credentials.**
{{< /aside >}}

### File structure and running programs

### Writing code

## Troubleshooting

{{< include_resource "resource_troubleshooting" >}}

# Your first Pi project!

## Programming on Pi

For the first coding project you will create a trivia game.  

## Pi Hardware

Now that your trivia game is up and running, we will utilize the GPIO pins on the Raspberry Pi and an LED sensor to signal a correct or incorrect guess to the user. 

### GPIO Pins
To activate the LED, you must communicate to the Raspberry Pi which GPIO pins are being utilized.  

Try editing your `rgb.py` file to activate the lights.

| Function |       Input      |   Example Use  | Explanation                                                                                                                      |
|:--------:|:----------------:|:--------------:|----------------------------------------------------------------------------------------------------------------------------------|
|  forward |      amount      |  forward(100)  | Moves the turtle forward by the specified amount                                                                                 |
| backward |      amount      |  backward(100) | Moves the turtle backward by the specified amount                                                                                |
|   right  | angle in degrees |    right(45)   | Turns the turtle clockwise by the specified angle                                                                                |
|   left   | angle in degress |    left(45)    | Turns the turtle counter clockwise by the specified angle                                                                        |
|   color  |     colorname    |  color("red")  | Sets the color for drawing. Use "red", "black", etc.  Here's a list of all the colors.                                           |
|   shape  |     shapename    | shape("arrow") | Should be "arrow", "classic", "turtle", or "circle"                                                                              |
|   speed  | number from 0-10 |    speed(0)    | Determines the speed at which the turtle moves around the window. 1 for slowest, 3 for normal speed, 10 for fast, 0 for fastest. |
|  pendown |       None       |    pendown()   | Puts down the turtle/pen so that it draws when it moves                                                                          |
|   penup  |       None       |     penup()    | Picks up the turtle/pen so that it doesn’t draw when it moves                                                                    |
| pensize  |       width      |   pensize(4)   | Sets the width of the pen for drawing                                                                                            |

