---
title: 6. Functions
type: labs
resources:
- name: test_part_b() output
  src: images/courses/cs9/unit00/00_functions_fig_b.png  
- name: draw_forest(10) output
  src: images/courses/cs9/unit00/00_functions_forest.png
#draft: true

---
# Functions Lab

In this lab, we will learn how to create and call functions. Functions are blocks of code that are reusable throughout a program. You've already encourated functions such as `print()`, which is a function built into Python.


## [0] What is a function?
Before we can talk about functions, we need to talk about code blocks. A **code block** is one or more lines of code. Here's one:

```python
forward(side_length)
left(120)
```

Sometimes we want to talk about how many times a code block should run, or whether it should run at all.
Consider this code, which will draw a triangle:

```python
for each_item in range(3):
    forward(side_length)
    left(120)
```

We have the same code block, but now it's indented under the condition `for each_item in range(3):`. This means
the code block should run once for each item in the range. A few things to note:

- Whenever a code block is indented, there's always a line introducing it. This line always ends with a colon.
- The way you indent matters. **Always use the tab key to indent.**
- When you're done with a code block, just stop indenting.

Often times we want to reuse a code block in different sections of a program. `Functions` allow for code reuse without needing to copy and paste code blocks. Here is a function:

```python
def draw_triangle(side_length):
    #This function draws a triangle
    for i in range(3):
        forward(side_length)
        left(120)
```

A few things to note:

- The structure of the function definition looks a lot like a for-loop. There's an introduction line ending in a colon, and then an indented code block.
- The `def` keyword tells the computer you're defining a new function.
- The function's name, `draw_triangle`, comes right after `def`. You could call a function `x` but you'll regret it :)
- After the function's name is the list of arguments, surrounded by parentheses `(side_length)`. Arguments, or parameters, are the things you need to tell the program before you can use the function. Think of arguments as questions the program might ask about what to do. For `draw_triangle`, the program wants to know "How long should the length of the sides be?" and you have to tell it the `side_length`. Some functions won't have any arguments, so their parameters list will look like `()`. It depends how you design your functions.
- The first line of the function's code block should be a comment explaining what the function does.
- In the function's code block, you can use the arguments as variables.


{{< aside >}}
**Functions make your code simpler.** Instead of writing all the code for a triangle over and over, you can get it right once and put it in a function.

Once you have written a function, you must call it. Calling a function tells Python to run that block of code. Remember, order matters. **Code is read from top to bottom.** You cannot call a function before it has been written.

{{< /aside >}}



<br>

{{< checkpoint >}}

Look at the code below. Answer the questions in your notebook before moving on:


0.  What argument does the `hexagon` function take?
0.  How is that argument used in the `hexagon` function?
0.  What line of code is the `hexagon` function called?
0.  What line of code is the `draw_pattern` function called?

```python
def hexagon(side_length):
   #Draws a hexagon"
   for i in range(6):
       forward(side_length)
       right(360//6)

def draw_pattern():
    #Draws a hexagon pattern
    for each_side in range(6):
        pendown()
        hexagon(20)
        penup()
        forward(20)
        left(360 / 6)

draw_pattern()
```

*This program will draw the below pattern.*
{{< figure src="images/courses/cs9/unit00/00_functions_hexagon.png" width="300px">}}

{{< /checkpoint >}}



---

## [1] Combining functions

When you want to draw something fancy, you need to break it down into smaller steps. Then you can write functions to do the smaller steps, and write more functions to combine small steps into bigger steps. This concept is called **decomposition**.

The code in part **B** illustrates this. If we want to draw an ice cream cone with scoops of ice cream, we can break it down into steps:

- Draw ice cream: `draw_icecream(num_scoops)`
    - Draw an ice cream cone: `cone()`
    - Draw a scoop of ice cream: `icecream_scoop()`
    - Move the turtle between scoops: `setup(x,y)`

{{< code-action >}} Create a new file in your `cs9/unit_00` directory called `lab_06_functions.py`
  and paste in this starter code.
  Your job is to write the functions: `draw_icecream(num_scoops)`, `cone()`, and `icecream_scoop()`

```python
#################################
# Unit 0 Lab 4
# Author: Emma Brown
#################################

from turtle import *

def setup(x, y):
    '''Sets up the turtle, ready to draw,
    at the given coordinates'''
    penup()
    goto(x, y)
    pendown()
    speed(0)
    setheading(0)


#################################
showturtle() #Shows the turtle as it draws

# B. COMBINING FUNCTIONS

def cone():
    "Draws an ice cream cone"
    # YOUR CODE HERE


def icecream_scoop():
    '''Draws one scoop of ice cream.'''
    # YOUR CODE HERE


#YOUR draw_icecream() FUNCTION GOES HERE
    '''Draws an ice cream cone
    with the ice cream scoop on top.
    Use the function setup() to set the placement of the drawing.'''

#CALL DRAW ICE CREAM FUNCTION HERE

#Hides the turtle pen and keeps it open until key press
hideturtle()
input("Press enter to end program...")

```

{{<aside "Optional: How to Fill a Shape with Color and More!">}}
To fill your turtle drawing with color follow the below format. You must call `begin_fill()` before the shape has been drawn and `end_fill()` after.

```python
def draw_triangle(sideLength):
    #This function draws a triangle
    for i in range(3):
        left(120)
        forward(sideLength)

fillcolor("Blue")
begin_fill()        #Tells the turtle to start the color fill
draw_triangle(20)
end_fill()          #Tells the turtle to stop the color fill
```
<br>

*For a wide range of color options look at this [chart](http://cng.seas.rochester.edu/CNG/docs/x11color.html).*

{{</aside>}}

A completed part **B** will look similar to the image below. The colors of the cone and ice cream scoops are up to you!

{{< figure src="images/courses/cs9/unit00/00_functions_icecream.png" width="200px">}}


---

## [2] Writing Functions

{{< code-action >}} Your job is to write the functions: `square(side-length)`, and `drawGrid(square_size, gap)`.
 Paste in this starter code below into your `lab_06_functions.py` file:

```python

# C. WRITING CODE


def square(side_length):
    '''Draws a square using `side_length` as the length'''
    #YOUR CODE GOES HERE


def drawGrid(square_size,gap):
    '''
    - Draw a grid of squares using nested for loops.
    - Use the function `setup()` to move the turtle.
    - `square_size` should set the size of the square
    - `gap` should adjust the size of the gap inbetween the squares in the grid
    '''
    #YOUR CODE GOES HERE


#CALL DRAW GRID FUNCTION HERE


#Hides the turtle pen and keeps it open until key press
hideturtle()     
input("Press enter to end drawing...")
clearscreen()
```

Let's practice writing some functions. Fill in the code blocks for the functions in part **C**. If you succeed, you'll get an image similar to the one below.



{{< figure src="images/courses/cs9/unit00/00_functions_grid.png" width="400px">}}

---

{{< checkpoint >}}

Answer the following questions in your notebook before moving on:

0.  How did you decide where to call the `square()` function?
0.  How did you use loops to create a grid?

{{< /checkpoint >}}

---
## [3] Deliverables
{{< deliverables "For this lab, you should submit the following:" >}}


- The your `lab_06_functions.py` file with the code you wrote for each of the parts
- Your notebook with responses to the checkpoint questions

{{< /deliverables >}}
## [4] Extension
