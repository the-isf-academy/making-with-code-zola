---
title: 0. Trivia Time
type: labs
---

# Fresh Baked Pi 🥧


### **[1] Trivia File**

{{< code-action >}} Start by running `python3 game.py t` on your Pi over an SSH connection.

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
$ python3 game.py t
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
$ python3 game.py p
```
Did the LED work as you expected? If not, review the hardware and the `PiView` class.

# **Deliverables**
Congratulations on completing your first Raspberry Pi project! We hope you enjoyed this introduction to the Raspberry Pi and its many functions.

To submit this lab please:
- Make sure your `random_choices()`, `check_guess()`, and `play()` functions pass the test harness. Running
`python3 test_lab.py` should return no errors.
- Take a picture of your Pi with the LED connected (and on!). Add this file to your git repository.
- Commit your code and push to Github.
