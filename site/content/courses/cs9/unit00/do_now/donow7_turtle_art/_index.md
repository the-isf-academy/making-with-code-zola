---
title: 6. Turtle Art
type: checkup
#draft: false
---

# Turtle Art

{{< code-action "Create a new file in your" >}} `do_now` **folder.**
```shell
cd Desktop/cs9/unit_00/
cd do_now
atom donow7.py
```
## Image to Copy
{{< figure src="images/courses/cs9/unit00/blue_hexagon.png" width="50%" >}}

{{< code-action "In your `donow7.py` file, try to recreate this turtle drawing as closely as you can." >}} Feel free to copy and paste this starter code. 

```python
#############
# donow7.py
#############

from turtle import *

```
### [Turtle Resources]

{{< look-action >}} **Here are resources to remind you what you can do with turtle:**


| Function |       Input      |   Example Use  | Explanation                                                                                                                      |
|:--------:|:----------------:|:--------------:|----------------------------------------------------------------------------------------------------------------------------------|
|  forward |      amount      |  forward(100)  | Moves the turtle forward by the specified amount                                                                                 |
| backward |      amount      |  backward(100) | Moves the turtle backward by the specified amount                                                                                |
|   right  | angle in degrees |    right(45)   | Turns the turtle clockwise by the specified angle                                                                                |
|   left   | angle in degress |    left(45)    | Turns the turtle counter clockwise by the specified angle                                                                        |
|   color  |     colorname    |  color("red")  | Sets the color for drawing. Use "red", "black", etc.  
|   pencolor  |     colorname    |  pencolor("red")  | Sets the color for the pen. Use "red", "black", etc.  
|   fillcolor  |     colorname    |  fillcolor("red")  | Sets the color to fill in the shape. Use "red", "black", etc.  
|   begin_fill  |     None    |  begin_fill()  | Use this before you begin drawing the outline that you want to fill.  
|   end_fill  |     None    |  end_fill()  | Use this after you finish drawing the outline that you want to fill.    
|   shape  |     shapename    | shape("arrow") | Sets the shape of the turtle itself. Should be "arrow", "classic", "turtle", or "circle"                                                                              |
|   speed  | number from 0-10 |    speed(0)    | Determines the speed at which the turtle moves around the window. 1 for slowest, 3 for normal speed, 10 for fast, 0 for fastest. |
|  pendown |       None       |    pendown()   | Puts down the turtle/pen so that it draws when it moves                                                                          |
|   penup  |       None       |     penup()    | Picks up the turtle/pen so that it doesn’t draw when it moves                                                                    |
| pensize  |       width      |   pensize(4)   | Sets the width of the pen for drawing      

{{< look-action >}} **Here are examples of** [colors](http://pudgyfish123.weebly.com/pythonroom.html) **you can use with turtle:**

{{< figure src="images/courses/cs9/unit00/turtle_colors.jpeg" width="100%"  >}}
