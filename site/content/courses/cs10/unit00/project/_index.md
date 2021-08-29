---
Title: Hardware Project
draft: False
---

# Unit 00 Hardware Project
Raspberry Pi's are tiny but powerful computers that can be used for tons of DIY projects. Since Raspberry
Pi's are so small but have full computational, networking, and hardware capabilities, they are great tools
for making robots, internet-of-things devices, networking services, and much more.

## [0] Pseudocode
You've seen a demonstration of a Raspberry Pi that's connected to an LED light and a press-button. When the button is pushed in, the LED lights up. When the button is released, the light turns off.

{{< write-action "Write pseudocode that describes how you think the button-activated LED works." >}}

## [1] Raspberry Pi Set Up


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
