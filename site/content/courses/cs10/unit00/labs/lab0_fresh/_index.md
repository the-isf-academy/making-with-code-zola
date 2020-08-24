---
title: "0. Freshly Baked Pi"
type: lab
---

# Fresh Baked Pi 🥧
This year, you'll be using Raspberry Pi's as our computational companions. Before you get too excited, these
are not warm, flakey baked goods, these are tiny computers built entirely on a single circuit board.

But even if these Pi's might not be as tasty as edible raspberry pies, they are still pretty exciting!

## Raspberry what?
Raspberry Pi's are tiny but powerful computers that can be used for tons of DIY projects. Since Raspberry
Pi's are so small but have full computational, networking, and hardware capabilities, they are great tools
for making robots, internet of things devices, networking services, and much more.

{{< look-action >}} Check out some of the projects you can make with Raspberry Pi's:

{{< youtube "ZXpGNBzHKRY" >}}

### Unboxing
The first unit of cs10 will help you get comfortable using your Raspberry Pi by exploring the practice of
working over a network, the Linux-based operating system Raspbian, and the basics of the Pi's hardware.

We'll provide more materials over the course of the year, but for now your Raspberry Pi kit should look
like this:

{{< figure src="images/courses/cs10/unit00/00_fresh_rpikit.png" width="100%" title="Raspberry Pi cs10 Starter Kit" >}}

Here's what's included:
- 1 Raspberry Pi 3B+
- 1 microSD card imaged with the operating sytem and configs we'll use for the course
- 1 Raspberry Pi case
- 1 USB C (or USB 3) to Micro-USB power cable
- 8 female to female jumpers
- 1 3-color LED component
- 1 temperature sensor (or temperature/humidity sensor)

We will talk more about the hardware components of the Pi in a future unit, but here's a diagram of each of the
parts if you are interested. You can take your Pi out of the case to see what it's made of.

{{< figure src="images/courses/cs10/unit00/00_fresh_rpidiagram.png" width="100%" title="Raspberry Pi component diagram" >}}

**You will be using your Pi all year, so you've got to take good care of it! Treat it like you would treat
a newborn baby if the baby were a computer you were building.**

### Setup
Now that you've got a sense of the layout of your Pi, let's get setup so you can start coding with it.

{{< aside >}}
Before you run the setup script, make sure you know the name and password of your home wifi network.
If you know that your wifi network has special settings, talk to a teacher before beginning the setup.

**Currently, the setup script does not work if your wifi network's password contains a space. If this is the case,
please tell {{< teacher >}} before starting the setup.**
{{< /aside >}}

#### Connect to Pi's hotspot
0. Take the USB to MicroUSB cable and plug your Pi in. You can plug it into your computer or into a power
outlet with a USB power plug. The red and green lights on the side of your Pi should turn on and flash once
it is powered.
0. Give your Pi a minute or two to boot up. Once it has booted, it will begin broadcasting a wifi signal called
`RPiHotspotN` where `N` is the number on your Pi.
    > *If you don't see the Pi's network. Try reboot your Pi by unplugging it and plugging it back in. If you
    still don't see the network, try manually adding the network on your computer using `Join other network...`
    and entering the Pi's network name (`RPiHotspotN`), selecting `WPA/WPA2 Personal` for the security setting, and
    entering the password `cs10_setup`.*
0. Connect your computer to this wifi network using the password `cs10_setup`.
    > *This wifi network will not
    have access to the internet. You will have to temporarily leave the Google Meet. If you have a problem during setup,
    you will need to reconnect to your regular wifi network and rejoin the Google Meet.*

#### Pi Setup Script
0. Once you are connected to the Pi's hotspot, open a Terminal window on your computer.
0. Type the following into your terminal window: `ssh setup@192.168.50.5`
0. When prompted for a password, enter `setup`. Once this command runs, you will be remotely controlling the Pi
through the wifi network it is broadcasting!
0. The Pi will automatically run a setup script. Choose option `0`.
0. Follow the instructions in the script to setup up a new user.
    > *Your username must not contain any spaces. Only
    the first word you enter will be used.*
0. Follow the instructions to add your home wifi network into the Pi's network settings.
0. After you finish the setup script, your Pi will reboot and your remote connection will be closed.

Reconnect your computer to your regular wifi network and rejoin the Google Meet.

### Using Pi
Your Pi should now be connected to your home wifi network. Now you can connect to it remotely with your computer and
it will have access to the internet!

#### Connecting to your Pi (SSH)
Once your Pi is connected to your home wifi network, you can remotely connect to it with your computer through your wifi router.
To understand how this works, you'll need to learn some basics of networking.

{{< include_resource "resource_network_basics" >}}

Since both your Pi and your home computer are connected to your home wifi network, you
can connect to your Pi using your computer using a Secure Shell (SSH) connection.

{{< code-action >}} Follow the steps below to connect to your Pi:

0. Make sure your computer is connected to your home wifi network
0. In a terminal window, run the command `arp -a`. This will list all the devices
on your home wifi network.
0. Look for the device labeled `raspberrypi`. If you see it, your Pi has connected to your
regular wifi network!
0. Run the command `ssh USER@raspberrypi`, replacing `USER` with the username you created
in the setup.
0. Enter the user password you used during the setup when prompted for a password.
0. You should now be remotely connected to your Pi! You'll know when you've connected
to the Pi because your prompt will change to be `YOUR_USER@raspberrypi:~ $`

{{< aside >}}
If you cannot find a `raspberrypi` device on your wifi network, wait a couple minutes
to allow the Pi to reboot and connect to the internet. Try running the `arp -a` command a couple times.
If the problem persists, you may need to re-enter your wifi password. You can do this by reconnecting
to the `RPiHotspotN` wifi network, running `ssh setup@192.168.50.5` (password "setup"), choosing
option 2 from the setup, and reentering your wifi credentials.

**If you are able to connect to your Pi's wifi hotspot, it has not been able to connect to a wifi network
and you'll need to re-enter the wifi credentials.**
{{< /aside >}}

{{< checkpoint >}}
Stop once you've reached this point and make sure everyone in your group has completed the initial
Pi setup.

Check in with {{< teacher >}} before moving on.
{{< /checkpoint >}}

#### File structure
Because you are remotely connected to your Pi through your Terminal, the Terminal is the only interface
you have to naviagte the file structure and run programs. Fortunately, you have tons of experience with
this tool from cs9. If you need a refresher, check out the Terminal lab from cs9.

When you log in to your Pi, you will be taken to the home (`~`) directory of your user. There's no
Desktop on the Pi, so we'll treat this as out home base. Just like in cs9, cs10 will have it's own
direcctory with a directory for each unit and more directories for each lab or project.

{{< code-action >}} Run the following commands to make two new directories:

```shell
$ mkdir cs10
$ cd cs10
$ mkdir unit_00
$ cd unit_00
```

#### Writing code

The remote connection to the Raspberry Pi also means that there is no graphical interface for text
editing. You can't run Atom on the Pi, only editors that run inside the Terminal.
However, there is a way to use a graphical text editor on your computer to edit the files on a remote
device like your Pi. To do this, we need to connect Atom to the SSH tool you use to access your Pi.

{{< tabs id="SSH Tunneling Setup" >}}
{{< tab "MacOS" >}}

{{< code-action >}} To set up remote text editing over SSH, run the following
commands **in a Terminal window on your computer** (you may need to put in the password
for your computer):
```shell
$ sudo apm install remote-atom
$ echo '  "remote-atom":\n    launch_at_startup: true' >> ~/.atom/config.cson
$ echo "\nHost raspberrypi\n\tRemoteForward 52698 localhost:52698\n\tUser user" >> ~/.ssh/config
```

{{< code-action >}} Now, run the following lines **on your Pi over an SSH connection**:
```shell
$ sudo curl -o /usr/local/bin/rmate https://raw.githubusercontent.com/aurora/rmate/master/rmate
$ sudo chmod +x /usr/local/bin/rmate
$ sudo mv /usr/local/bin/rmate /usr/local/bin/ratom
```

Now, whenever Atom is open on your computer and you are connected to your Pi via SSH,
you can use `ratom file.py` to open a file from the Pi in Atom on your computer!
{{< /tab >}}

{{< tab "Windows" >}}
{{< code-action >}} To set up remote text editing over SSH, run the following
commands **in a Powershell window on your computer** (you may need to put in the password
for your computer):
```shell
$ apm install remote-atom
$ echo "  `"remote-atom`":`n    launch_at_startup: true" | Out-File -FilePath ~/.atom/config.cson -Append -Encoding ASCII
$ echo "`nHost raspberrypi`n`tRemoteForward 52698 127.0.0.1:52698`n`tUser user" | Out-File -FilePath ~/.ssh/config -Append -Encoding ASCII
```

{{< code-action >}} Now, run the following lines **on your Pi over an SSH connection**:
```shell
$ sudo curl -o /usr/local/bin/rmate https://raw.githubusercontent.com/aurora/rmate/master/rmate
$ sudo chmod +x /usr/local/bin/rmate
$ sudo mv /usr/local/bin/rmate /usr/local/bin/ratom
```

Now, whenever Atom is open on your computer and you are connected to your Pi via SSH,
you can use `ratom file.py` to open a file from the Pi in Atom on your computer!

{{< /tab >}}
{{< /tabs >}}
{{< aside >}}
If you would like to try using a text editor in the Terminal, you can read about [vim](https://www.tutorialspoint.com/vim/vim_introduction.htm)
or [emacs](http://www.jesshamrick.com/2012/09/10/absolute-beginners-guide-to-emacs/),
two popular command line text editors. Talk to {{< teacher >}} if you have any questions.
{{< /aside >}}

{{< code-action >}} Let's try this out!

0. Close your current SSH connection with `exit` and start it again with `ssh USER@raspberrypi`
0. Create a new file using `ratom hello_world.py`.
0. Type whatever python code you want to into the file that opens on your computer (maybe
`print("Hello world!")`
0. Save and close the file.

#### Running code
Now that you have a Python file on your Pi, you can run your very first Python program from
a Raspberry Pi.

{{< code-action >}} Run the following command on your Pi:
```shell
python3 hello_world.py
```

Congrats! You are all ready to get started on your first Raspberry Pi project!

{{< aside >}}
Notice that you need to explicitly use `python3` to run your files on your Pi,
not just `python`.
{{< /aside >}}

{{< checkpoint >}}
Stop once you've reached this point and make sure everyone in your group has completed the initial
Pi setup.

Check in with {{< teacher >}} before moving on.
{{< /checkpoint >}}

# Your First Pi Project

## **Programming on Pi**

For the first coding project you will create a trivia game.

Your tasks:

1. Reacquaint yourself with Python
2. Familiarize yourself with coding on the Raspberry Pi
2. Play and redesign the trivia game

### **[0] Setup**

To get started, we need to configure the git settings on your Pi so you can push and pull
from GitHub. 

{{< code-action >}} Enter the following command on your Pi over SSH:

```shell
git config --global user.name <Your name>
git config --global user.email <Your school email>
git config --global core.editor "ratom --wait"
git config --global commit.template .commit_template
git config --global credential.helper store
```
 A respository has been created for you with your Github username.

{{< code-action >}} Clone it to your Pi over SSH using the following command (replace
`YOUR_GITHUB_USERNAME` with your Github username):

```
$ git clone https://github.com/the-isf-academy/lab-trivia-YOUR_GITHUB_USERNAME.git
```

<br>

### **[1] Trivia File**

{{< code-action >}} Start by running `python3 game.py` on your Pi over an SSH connection.

This program plays a basic version of the trivia game you will be completing for this lab.

The `trivia.txt` file contains the questions used in the game. When everyone has completed the lab, we will take turns playing through everyone's game.

The format for the question types can be found in the `README.md`.

<br>

{{< code-action >}} Start by customise `trivia.txt` to questions of your choosing. For now, don't add more than
3 question (you can add more after you finish the other parts of the lab).

<br>

### **[2] Classes *and* games**
In this lab, we'll work to remind ourselves of classes and objects by building a text-based trivia game.

For your reference, we will start by focusing on the `TerminalView` of the Trivia Game which utilizes the following classes. Make sure your model includes each of them.

- Game
- View
    - TerminalView
- Question

{{< write-action >}} Read through the documentation pages and make a model for how this implementation of Trivia Game works.

<br>

{{< aside >}}
If you need a refresher on Classes, please reference the below resources.

**Constructors:** [12.5 Constructors](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_5)

**Inheritance:** [12.6 Inheritance](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_6)
{{< /aside >}}

<br>

As the program reads `trivia.txt` creates a `Question` object for each trivia prompt. However, the Question
class has some bugs. 

#### [2.A] `random_choices()`
{{< code-action >}} Edit `random_choices()` to return a list of the choices for the question in a different random order every time it is called.

#### [2.B] `check_guess()`
{{< code-action >}} Edit `check_guess()` to take as input the player’s guess and check to see whether the guess matches the correct answer. If the guess is correct. The function should return True. If the guess is incorrect, the function should return False.

#### [2.C] `play()`
In the `game.py` file, the `play()` function only plays one round of the game.

{{< code-action >}} Fill in the `play()` function in game.py. The function should iterate through a list of `Question` objects and use the `View` class to receive input and display information. After each question, it should tell the user if they answered correctly or incorrectly. At the end of the game, it should display the user's score.

<br>

### **[3] Play Game**

{{< code-action >}} Now that you've got a model for the Trivia Game software, play through a game by running the following command in your terminal:

```shell
python game.py t
```
Was the gameplay different than you expected? Check you model to see if it still makes sense and change it up if it doesn't.

{{< checkpoint >}}
Stop once you've reached this point and make sure everyone in your group has completed the initial
Pi setup.

Check in with {{< teacher >}} before moving on.
{{< /checkpoint >}}

## **Pi Hardware**

Now that your trivia game is up and running, we will utilize the GPIO pins on the Raspberry Pi and an LED sensor to signal a correct or incorrect guess to the user.

Your tasks:

1. Familiarize yourself with the GPIO pins  
2. Light up the LED through code and hardware
2. Play and redesign the trivia game with LED sensor


### **[4] Classes, games, *and* hardware**
In this section of the lab, we'll incorporate hardware into our trivia game to create visual feedback.

We will now focus on the `PiView` of the Trivia Game which has the following classes. Please note the addition of the `PiView` and `RBILight` class. {{< write-action >}} Make sure your model includes all of them.

- Game
- View
    - TerminalView
    - PiView
- Question
- RGBLight

### **[5] Hardware Set Up**
Let's begin by connecting our LED sensor to the Raspberry Pi.

To connect the LED to the Raspberry Pi you will need:
- 1 Raspberry Pi
- 4 female-to-female jumper cables
- 1 3-color LED component

*Below is a diagram of the GPIO pins. Each pin has a specific function and a pin number. For this lab we will use 1 ground pin and 3 GPIO pins. Reference the pin numbers and pin functions when connecting the LED.*

{{< figure src="images/courses/cs10/unit00/00_fresh_gpiodiagram.png" width="100%" >}}


*This is how your Raspberry Pi will look when hooked up to the LED.*
{{< figure src="images/courses/cs10/unit00/00_fresh_gpioconnection.png" width="100%"  >}}

*Although the wires below are color coded, it is not necessary to do so.*
{{< figure src="images/courses/cs10/unit00/00_fresh_rgbsensor.png" width="100%"  >}}


By connecting the `R, G, and B` LED component pins to the GPIO pins of the Raspberry Pi, we are able to send power to each color. The `Ground` LED component pin completes the circuit, allowing power to flow through and power the LED.

<br>

{{< code-action >}} Hook up your LED sensor to your Raspberry Pi

0.  Connect `1 jumper wire` to the `9, 11, 13, and 15` pins
0.  Connect the `Pin 9` wire to the `Ground` LED component pin
0.  Connect the `Pin 11` wire to the `R` LED component pin
0.  Connect the `Pin 13` wire to the `G` LED component pin
0.  Connect the `Pin 15` wire to the `B` LED component pin



<br>

### **[6] Coding the LED**
Now that the LED is connected to the Raspberry Pi, we can integrate the LED into the Trivia game. By editing the `PiView` child class in `view.py` you will program the light to display different colors depending on if the user entered the correct or incorrect answer.

The `PiView` child class creates an instance of an LED object which is coded in the `rgb.py` file. By calling the `changecolor()` function on a `RGBLight` object, you can manipulate the color the LED emits. Each `R, G, and B` color pin work together to create one unified color. Each pin can be activated or deactived through binary code.

{{< aside >}}
Reference the below resources to learn more about RGB light and binary code.

**👀RGB Light:** [How an RGB LED works and how to use one! | Basic Electronics](https://www.youtube.com/watch?v=wqzfbImsrPE)

**👀Binary** [How exactly does binary code work? - José Américo N L F de Freitas](https://www.youtube.com/watch?v=wgbV6DLVezo)
{{< /aside >}}
<br>


*Review `changeColor()` in `rgb.py` and experiment with the function in the `PiView` class.*

#### 6.A `correctAnswer()`
{{< code-action >}} Edit `correctAnswer()` to set the color of the LED to green. For each question, the LED should light up green if the user answers correctly.

#### 6.B `wrongAnswer()`
{{< code-action >}} Edit `wrongAnswer()` to set the color of the LED to red. For each question, the LED should light up red if the user answers incorrectly.



<br>

{{< aside >}}
To learn more about how the GPIO pins communicate with Python, take a look at `rgb.py`. Reference the chart below to better understand how the LED is activated. Note how there is not a specific GPIO function for changing the color of the LED.

| Function |      Parameters     |  Explanation | Example Function                                                                                                                      |
|:--------:|:----------------:|:--------------:|:----------------------------------------------------------------------------------------------------------------------------------:|
|  setmode(arg) |      BOARD or BCM   |  Sets GPIO numbering mode                                                       |   setmode(BOARD)   |
| setup(arg,arg) |      PIN number, IN or OUT     |  Sets GPIO pin to receive input or send output |    setup(PIN,GPIO.OUT)                                                       |
| output(arg,arg) |      PIN number, HIGH or LOW     |  Sets GPIO pin to on or off |    output(PIN,GPIO.HIGH)                                                         |
|   cleanup()   | None |    Resets all GPIO pins used   | cleanup()

Steps to Turning Off and On the LED:
1.  Set PINS to output mode
2.  Set power of each color PIN to HIGH
3.  Set power of each color PIN to LOW
4.  Clean Up
{{< /aside >}}

<br>

### **[7] Play Game**

{{< code-action >}} Now that you've got an updated version of your Trivia Game software, play through a game by running the following command in your terminal:

```shell
python game.py p
```
Did the LED work as you expected? If not, review the hardware and the `PiView` class.

# **Deliverables**
Congratulations on completing your first Raspberry Pi project! We hope you enjoyed this introduction to the Raspberry Pi and its many functions.

To submit this lab please:
- Make sure your `random_choices()`, `check_guess()`, and `play()` functions pass the test harness. Running
`python3 test_lab.py` should return no errors.
- Take a picture of your Pi with the LED connected (and on!). Add this file to your git repository.
- Commit your code and push to Github.
