---
title: "0. Drawing Mini-Challenges"
type: checkup
---
# Do Now

Welcome back from break! Before we jump into Unit 02, let's do a little review.


{{< code-action "First, navigate to your cs9/donows folder, and create a" >}} `unit_01` **folder.**

```shell
cd Desktop/cs9
cd cs9-donows-YOUR-GITHUB-USERNAME
mkdir unit_02
cd unit_02
```

{{< code-action "Create a new document" >}}
```shell
atom donow0.py
```

{{< code-action "Paste in this starter code." >}}

```python
#############
# unit02
# donow0.py
#############

from turtle import *
#make the drawing appear instantly
tracer(0, 0)

#---YOUR CODE GOES HERE---#
forward(100)


# updates, hides the turtle, and keeps the window open
update()
hideturtle()
input()
```

## Challenges

Below are series of Turtle drawings. It is up to you re-create them and customize them as you wish.

Each challenge builds on itself with increasing complexity. Be sure to go in chronological order.

{{< expand "Turtle Documentation" >}}

Here is a brief reminder of some Turtle functions. Feel free to reference the more comprehensive [documentation](https://docs.python.org/3/library/turtle.html).

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
{{< /expand >}}

### [Square Function]

{{< code-action >}} **Write a function called `draw_square()`.** It should take `side_length` as a parameter.


{{< figure src="images/courses/cs9/unit02/donow0_0.png" width="50%" alt-title="step 1" >}}

{{< code-action "Add the ability to customize the pen color." >}} Your function should now take `custom_color` as a parameter.

{{< figure src="images/courses/cs9/unit02/donow0_1.png" width="40%" alt-title="step 1" >}}


### [Square Pattern]

{{< code-action >}} **Write a function called `draw_pattern()` that uses the `draw_square()` to create a star pattern.** It should take `num_points` as a parameter.

{{< figure src="images/courses/cs9/unit02/donow0_2.png" width="40%" alt-title="step 1" >}}


{{< code-action >}} **Use a list to create a more colorful pattern.** `draw_pattern()` should now take `color_list` as a parameter. It should cycle through the list each time it draws a square.
> *Feel to reference [this](https://trinket.io/docs/colors) list of Turtle colors*


{{< figure src="images/courses/cs9/unit02/donow0_3.png" width="40%" alt-title="step 1" >}}

{{< code-action >}} **Experiment with `draw_pattern()`!** Try to create the image below. Explore different color combinations.


{{< figure src="images/courses/cs9/unit02/donow0_4.png" width="50%" alt-title="step 1" >}}

{{< deliverables "Be sure to push this Do Now to Github:" >}}

- `git status`
- `git add donow0.py`
- `git commit`
- `git push`

{{< /deliverables >}}


## Extension: Geometric Chaos

{{< code-action "Now that you've re-familiarized yourself with Python and Turtle, create your own geometric pattern." >}} *See below for some inspiration.*

[{{< figure src="https://www.101computing.net/wp/wp-content/uploads/Spirograph_Designs.jpg" width="100%" alt-title="step 1" >}}](https://www.101computing.net/wp/wp-content/uploads/Spirograph_Designs.jpg)

[{{< figure src="https://media.geeksforgeeks.org/wp-content/uploads/20200912205249/Screenshot730.png" width="80%" alt-title="step 1" >}}](https://media.geeksforgeeks.org/wp-content/uploads/20200912205249/Screenshot730.png)

[{{< figure src="https://pbs.twimg.com/media/DMXKU4MWkAAUD9s?format=jpg&name=4096x4096" width="80%" alt-title="step 1" >}}](https://twitter.com/margaritayong/status/920364309372424193/photo/1)
