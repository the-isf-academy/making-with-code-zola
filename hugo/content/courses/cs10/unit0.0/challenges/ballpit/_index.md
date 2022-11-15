---
title: 0. Ball Pit
type: lab
---

# Ball Pit

In this challenge, you will use your knowledge of classes to create a Turtle animation. 

## [0] Set up


{{< code-action  "Go to your CS10 folder" >}} 

```shell
cd ~/desktop/making-with-code/cs10/unit0.0_review
```

{{< code-action "Clone the repository" >}}

```shell
git clone https://github.com/the-isf-academy/lab_ballpit.git
```

{{< code-action "Go into the repo and enter the Poetry shell" >}}

```shell
cd lab_ballpit
poetry shell
```

This repository contains the following files:
- `ball.py`
- `ballpit.py`
- `setup_ballpit_canvas.py`
- `test_add_color_to_breathingball.py`
- `test_add_color_to_warpball.py`

---

## [1] Exploring Ball Pit

The Ballpit is a little animation made with Turtle. You can watch it by running the following command in your terminal:
 
```shell
python ballpit.py
```

{{< figure src="images/courses/cs10/unit00/lab-ballpit-00.png" width="400px" >}}

In the Ballpit, notice that each ball has a different behavior. One stays the same size the whole time and bounce off the walls. One doesn't bounce at all. Instead, it warps around to the opposite side of the screen. And the last ball grows and shrinks as it moves. It looks like it's breathing in and out.


For your reference, the BallPit has the following classes and functions. The `ball.py` file contains the architecture of each `Ball` object. The `ballpit.py` file initializes the Turtle and instances of the `Ball` objects. 

- `ball.py`
    - `Ball`
    - `WarpBall`
    - `BreathingBall`
- `ballpit.py`
    - `ball_pit()`

---

## [2] Increase the chaos

At the moment, each `Ball` object is the same shade of green. Wouldn't it be nice if we could distinguish them? Your goal is to add more color into the pit!

{{< code-action "Add a unique color to the WarpBall and the BreathingBall." >}} Currently the `WarpBall` and `BreathingBall` simply call the parent `Ball` method for `set_color()`. Overide this method with the colors of your choosing. 

{{< checkpoint >}}
In this lab we've included **test files** where you can experiment with changes to the `WarpBall` and `BreathingBall` separate from the ballpit. Run the following files to check if you've successfully changed the color of each object.
- `test_add_color_to_breathingball.py`
- `test_add_color_to_warpball.py`

{{< /checkpoint >}}

{{< code-action >}} **Let's try running `ballpit.py` again. You should see each `Ball` appear with a distinct color.**
```shell
python ballpit.py
```


Now that we've got the colors sorted, let's add to the chaos and add more balls to the pit. At the moment, there is only one of each type of `Ball` object displayed in the Turtle window. 

{{< code-action "Increase the amount of balls in the ballpit so each type of Ball appears at least 10 times." >}}

**Hint! Consider the following...*
- *What data strucutre currently holds the instances of `Ball`, `WarpBall`, and `BreathingBall`?*
- *What is the most code efficent solution?*


{{< figure src="images/courses/cs10/unit00/lab-ballpit-01.png" width="400px" >}}

---

### [Deliverables]

{{< deliverables >}}

Check-in with a teacher by demonstrating your improved `ballpit.py` file. 

{{< /deliverables >}}



---

## [3] Extension: Randomizing the chaos

If time allows, ramp up the chaos even further by introducing the idea of cycling through colors. For example, every time a `Ball` object is created, it selected a different shade of green. 

{{< code-action "Add a random element to the color of the Ball, WarpBall, and BreathingBall." >}} 

**Hint! Consider how the color is currently chosen in the `set_color()` method.*


{{< code-action "Embrace the chaos of the ball pit! Cause the Ball, WarpBall, and BreathingBall to change color as they move." >}} 

Be sure to push any customization you've made to your ballpit!

{{< figure src="images/courses/cs10/unit00/lab-ballpit-02.gif" width="400px" >}}

