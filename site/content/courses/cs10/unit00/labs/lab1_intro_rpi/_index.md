---
title: 1. Freshly Baked Pi
type: labs
# draft: true
---

# Fresh Baked Pi 🥧
Raspberry Pi's are tiny but powerful computers that can be used for tons of DIY projects. Since Raspberry Pi's are so small but have full computational, networking, and hardware capabilities, they are great tools
for making robots, internet-of-things devices, networking services, and much more.




## [0] Raspberry Pi Set Up

### [Setup Script]

0. Take the USB to MicroUSB cable and plug your Pi in. You can plug it into your computer or into a power outlet with a USB power plug. The red and green lights on the side of your Pi should turn on and flash once it is powered.
0. Connect your computer to the `RPIWIFI` network.
0. Type the following into your terminal window: `ssh setup@raspberrypi-N`. 
    > Replace `N` with your Raspberry Pi number. 
0. When prompted for a password, enter `setup`. Once this command runs, you will be remotely controlling the Pi
through the wifi network it is broadcasting!
0. The Pi will automatically run a setup script. Choose option `1. User Setup`.
0. Follow the instructions in the script to setup up a new user.
    > Your username must not contain any spaces. Only
    the first word you enter will be used.
    > It also must be all lowercase.
0. After you finish the setup script, your Pi will reboot and your remote connection will be closed.

### [sudo Access]

Before we move on, we need to grant you user account administrative access on your Pi. This will
also give you the chance to practice logging in and out of ssh connections.

0. Create a new ssh connection, this time to the `pi` account. You can use the command
`ssh pi@raspberrypi-N`
    > Replace `N` with your Raspberry Pi number. 
0. Enter the password `cs10_2020_teacher`
0. Once logged in, run the following command to give your user admin (or root) access (replace `<YOUR_USER>`
with the user you created in the setup):
    ```shell
    $ sudo usermod -aG sudo <YOUR_USER>
    ```
0. Enter the command `exit` to exit the current ssh connection
0. Reconnect with your user. `ssh YOUR_USERNAME@raspberrypi-N`
    > Replace `YOUR_USERNAME` with the user your created. 
    >
    > Replace `N` with your Raspberry Pi number. 
0. Run the command `groups` and make sure that `sudo` shows up in the list.

You now have root access which will allow you to install new programs on the Pi!


### [File structure & Updates]
Because you are remotely connected to your Pi through your Terminal, the Terminal is the only interface
you have to naviagte the file structure and run programs. Fortunately, you have tons of experience with
this tool from cs9. If you need a refresher, check out the Terminal lab from cs9.

When you log in to your Pi, you will be taken to the home (`~`) directory of your user. There's no
Desktop on the Pi, so we'll treat this as out home base. Just like in cs9, cs10 will have it's own
direcctory with a directory for each unit and more directories for each lab or project.

{{< code-action "Run the following commands to make two new directories" >}} 

```shell
$ mkdir cs10
$ cd cs10
$ mkdir unit_00
$ cd unit_00
```

{{< code-action "Update your Pi and install the required libraries. " >}} 

```shell
bash <(curl -sL https://raw.githubusercontent.com/the-isf-academy/courseware/master/cs9_student_setup/gpio_setup.sh)
```

### [Writing code]

The remote connection to the Raspberry Pi also means that there is no graphical interface for text
editing. You can't run Atom on the Pi, only editors that run inside the Terminal.
However, there is a way to use a graphical text editor on your computer to edit the files on a remote
device like your Pi. To do this, we need to connect Atom to the SSH tool you use to access your Pi.

{{< code-action >}} To set up remote text editing over SSH, run the following
commands **in a Terminal window on your computer** (you may need to put in the password
for your computer):
```shell
$ sudo apm install remote-atom
$ printf '  "remote-atom":\n    launch_at_startup: true' >> ~/.atom/config.cson
```

In the below command, for `raspberrypi-N` replace the `N` with your Pi number.
```shell
$ printf "Host raspberrypi-N\n\tRemoteForward 52698 localhost:52698\n\tUser user" >> ~/.ssh/config
```

{{< code-action >}} Now, run the following lines **on your Pi over an SSH connection**:
```shell
$ sudo curl -o /usr/local/bin/rmate https://raw.githubusercontent.com/aurora/rmate/master/rmate
$ sudo chmod +x /usr/local/bin/rmate
$ sudo mv /usr/local/bin/rmate /usr/local/bin/ratom
```

Now, **whenever Atom is open on your computer and you are connected to your Pi via SSH**, you can use `ratom file.py` to open a file from the Pi in Atom on your computer!


### [Running code]
Now that you have a Python file on your Pi, you can write and run your very first Python program from
a Raspberry Pi.

{{< code-action "Write your first Python file on your Pi!">}} It should print, `Hello World!`.


{{< code-action "Run the file" >}} and make sure it works as expected.
```shell
$ python3 hello_world.py
```

**Congrats! You are all ready to get started on your first Raspberry Pi project!**

### [Useful Raspberry Pi Commands]

| Command                | Description                          |
|------------------------|--------------------------------------|
| exit                   | exits the SSH connection             |
| sudo shutdown now      | shutdowns the Pi                     |
| reboot                 | reboots the Pi                       |
| ssh USER@raspberrypi-N | starts an SSH connect with your USER and your `N` numbered Pi |

## [1] Pseudocode
You've seen a demonstration of a Raspberry Pi that's connected to an LED light and a press-button. When the button is pushed in, the LED lights up. When the button is released, the light turns off.

{{< write-action "Write pseudocode that describes how you think the button-activated LED works." >}}

## [2] Using the LED

<br>

### [Hardware Set Up]
Let's begin by connecting our LED to the Raspberry Pi. To do this you will need:
- 1 Raspberry Pi
- 4 internal-to-internal jump wires
- 1 3-color LED component

*Below is a diagram of the General Purpose Input/Output (GPIO) pins. Each pin has a specific function and a pin number. For this first step we will use 1 Ground pin and 3 GPIO pins. Reference the pin numbers and pin functions when connecting the LED.*

{{< figure src="images/courses/cs10/unit00/00_fresh_gpiodiagram.png" width="100%" >}}

{{< code-action "Hook up your LED to your Raspberry Pi" >}}

0.  Connect `1 jumper wire` to the `9, 11, 13, and 15` pins
0.  Connect the `Pin 9` wire to the `-` LED component pin. This is the `Ground` pin.
0.  Connect the `Pin 11` wire to the `R` LED component pin
0.  Connect the `Pin 13` wire to the `G` LED component pin
0.  Connect the `Pin 15` wire to the `B` LED component pin

*This is how your Raspberry Pi will look when hooked up to the LED.*
{{< figure src="images/courses/cs10/unit00/00_fresh_gpioconnection.png" width="100%"  >}}

*Although the wires below are color coded, it is not necessary to do so.*
{{< figure src="images/courses/cs10/unit00/00_fresh_rgbsensor.png" width="100%"  >}}


By connecting the `R, G, and B` LED component pins to the GPIO pins of the Raspberry Pi, we are able to send power to each color. The `Ground` LED component pin (labelled with `-`) completes the circuit, allowing power to flow through and power the LED.

<br>

### [Coding the LED]
Now it's time to turn on our light!

{{< code-action "Clone the lab_sensors repository" >}} in your `cs10\unit_00` folder.
```shell
git clone https://github.com/the-isf-academy/lab-sensors-YOUR-GITHUB-USERNAME.git
```
{{< code-action "Create a simple program that turns the light on and off." >}}  Write your code in the file called `light_activated_button.py`

To get you started, here are a few basic methods from the `LED` class that you can use:
| Method |       Input      |   Example Use |  Explanation   |
|:--------:|:----------------:|:----------------------------:|--------------------------------------------------------------------------------------------------------------------|
|  _init | GPIO pin   |  led = LED(17) | creates an LED object for the given pin |
| off |      None      |  led.off() | Turns the device off |
|   on | None |    led.on()   | Turns the device on


{{< aside >}}
There's lots that you can do with the LED class, like making the LED blink indefinitely, and more! This is a great resource for you to use as you explore the Raspberry Pi:

**More LED Methods:** [LED documentation](https://gpiozero.readthedocs.io/en/stable/api_output.html#led)
{{< /aside >}}

## [3] Adding in the Button

### [Hardware Set Up]

Now we're going to connect our push-button to the Raspberry Pi. In addition to what you already have set up, you will need:
- 2 internal-to-internal jump wires
- 1 push-button component

0.  Connect `1 jumper wire` to the `37 and 39` pins
0.  Connect the `Pin 37` wire to the `-` LED component pin. This is the `Ground` pin.
0.  Connect the `Pin 39` wire to the `S` LED component pin

{{< figure src="images/courses/cs10/unit00/00_fresh_gpiodiagram.png" width="100%" >}}

### [Coding the Button]

In order to use the push-button, we'll use another `gpiozero` class, `Button`.

{{< code-action "Edit light_activated_button.py so that pressing the button turns the LED light on." >}}  

Here are some of the basic Button methods to get you started:

| Method |       Input      |   Example Use |  Explanation   |
|:--------:|:----------------:|:----------------------------:|--------------------------------------------------------------------------------------------------------------------|
|  _init | GPIO pin   |  button = Button(17) | creates an Button object for the given pin |
| is_pressed | None | button.is_pressed() | Returns True if the device is currently active and False otherwise |
| wait_for_press |     Number of seconds to wait before proceeding. If no parameter is given, it will wait indefinitely |  button.wait_for_press() | Pause the script until the device is activated, or the timeout is reached |
|   wait_for_release | Number of seconds to wait before proceeding. If no parameter is given, it will wait indefinitely |    button.wait_for_release()   | Pause the script until the device is deactivated, or the timeout is reached



{{< aside >}}
There's lots that you can do with the Button class, like choosing what happens when the button is held down for a certain number of seconds, and more! Click on the link to learn more methods!

**More Button Methods:** [Button documentation](https://gpiozero.readthedocs.io/en/stable/api_input.html#button)
{{< /aside >}}
<br>

### [Deliverables]

{{< deliverables "For this lab, you should push your lab-sensors repository containing updates to light_activated_button.py" >}}
<br>
Check in with the teacher by showing your button-activated light!
{{< /deliverables >}}
