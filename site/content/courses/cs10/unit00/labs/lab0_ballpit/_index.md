---
title: 0. Ball Pit
type: labs
---

# Ball Pit

Welcome to CS10! We hope you're excited for what we have planned this year! 😄

In this lab, we'll get re-aquainted with CS concepts such as classes and decomposition with the Turtle library. 

## [0] Set up

Now that you're in CS10, let's make a CS10 folder!

{{< code-action  "Run the code below in your terminal." >}} 

```shell
bash <(curl -sL https://raw.githubusercontent.com/the-isf-academy/courseware/master/cs9_student_setup/setupcs10_script.sh)
```


{{< code-action "Next, let's clone the repository" >}} in your `cs10\unit_00` folder. 

```shell
git clone https://github.com/the-isf-academy/lab-ball-world-YOUR-GITHUB-USERNAME.git
```


## [1] Exploring Ball Pit

The Ballpit is a little animation made with Turtle. You can watch it by running the following command in your terminal:
 
```shell
python ballpit.py
```

In the Ballpit, notice that each ball has a different behavior. One stays the same size the whole time and bounce off the walls. One doesn't bounce at all. Instead, it warps around to the opposite side of the screen. And the last ball grows and shrinks as it moves. It looks like it's breathing in and out.
 
Each different type of ball is represented by a different class. The normal bouncing balls are represented with the `Ball` class. This parent class has two child classes, `WarpBall` and `BreathingBall`. These two child classes inherit characteristics of the `Ball` class, and extend it to include additional features.  


{{< figure src="images/courses/cs10/unit00/lab-ballworld-00.png" width="400px" >}}


### [Create a Model]

The BallPit contains multiple types of objects with multiple properties. Before you jump into tinkering with the code, create a model for each object. 

{{< write-action "With your knowledge of classes and inheritance, draw a model with your partner for how the BallPit works." >}}

For your reference, the BallPit has the following classes and functions. The `ball.py` file contains the architecture of each `Ball` object. The `ballpit.py` file initializes the Turtle and instances of the `Ball` objects. Make sure your model includes each of them.

- `ball.py`
    - `Ball`
    - `WarpBall`
    - `BreathingBall`
- `ballpit.py`
    - `ball_pit()`

{{< aside "Explore these resources for reminder of how objects operate in Python." >}}

- Creating a Class: [12.5 Constructors](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_5)
- Inheritance: [12.6 Inheritance](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_6)
{{< /aside >}}



## [2] Increase the chaos

At the moment, there is only one of each type of `Ball` object displayed in the Turtle window. Let's add to the chaos and add more balls to the pit. 

{{< code-action "Increase the amount of balls in the ballpit so each type of Ball appears at least 10 times." >}}

{{< aside "Consider the following..." >}}
- What data structure currently holds the instances of `Ball`, `WarpBall`, and `BreathingBall`?
- What is the most code efficent solution? 
{{< /aside >}}

Now that we've increased the amount of balls in the pit, wouldn't it be nice if we could distinguish them? At the moment each ball is the same shade of green. Your goal is to add more color into the pit!  

{{< code-action "Add color to the WarpBall and BreathingBall." >}} Currently the `WarpBall` and `BreathingBall` simply call the parent `Ball` method for `set_color()`. Overide this method with the colors of your choosing. 

{{< figure src="images/courses/cs10/unit00/lab-ballworld-01.png" width="400px" >}}

## [3] Extension: Randomizing the chaos

Let's explore colors even further by introducing the idea of cycling through colors. For example, every time a `Ball` object is created, it selected a different shade of green. 

{{< code-action "Add a random element to the color of the Ball, WarpBall, and BreathingBall." >}} 

{{< aside "Consider the following..." >}}
- Take a look at how the color is being set with RGB values. 
{{< /aside >}}

To fully embrace the chaos of the ball pit, let's change the color of the balls as they move. 

{{< code-action "Cause the Ball, WarpBall, and BreathingBall to change color as it moves." >}} 


{{< figure src="images/courses/cs10/unit00/lab-ballworld-02.gif" width="400px" >}}


