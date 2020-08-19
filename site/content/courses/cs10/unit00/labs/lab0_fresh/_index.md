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

**Note: before you run the setup script, make sure you know the name and password of your home wifi network.
If you know that your wifi network has special settings, talk to a teacher before beginning the setup.**

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
0. When prompted for a password, enter `setup`. Once this command runs, you will be remotely controlling the Pi through the wifi network it is broadcasting!
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

### File structure and running programs

### Writing code

## Troubleshooting

{{< include_resource "resource_troubleshooting" >}}

# Your first Pi project!

## Programming on Pi

## Pi Hardware
