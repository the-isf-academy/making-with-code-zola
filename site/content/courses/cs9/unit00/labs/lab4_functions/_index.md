---
title: 4. Functions
type: labs
resources:
- name: test_part_b() output
  src: images/courses/cs9/unit00/00_functions_fig_b.png  
- name: draw_forest(10) output
  src: images/courses/cs9/unit00/00_functions_forest.png

---
# Functions Lab

In this lab, we will learn how to create and call functions. Functions are blocks of code that are reusable throughout a program. You've already encourated functions such as `print()`, which is a function built into Python. 


## A. What is a function? 
Before we can talk about functions, we need to talk about code blocks. A **code block** is one or more lines of code. Here's one:

```python
forward(100)
right(60)
```

Sometimes we want to talk about how many times a code block should run, or whether it should run at all.
Consider this code, which will draw a triangle:

```python
for each_item in range(3):
    forward(100)
    right(60)
```

We have the same code block, but now it's indented under the condition `for each_item in range(3):`. This means
the code block should run once for each item in the range. A few things to note:

- Whenever a code block is indented, there's always a line introducing it. This line always ends with a colon.
- The way you indent matters. **Always use the tab key to indent.**
- When you're done with a code block, just stop indenting.

Often times we want to reuse a code block in different sections of a program. `Functions` allow for code reuse without needing to copy and paste code blocks. Here is a function:

```python
def draw_triangle(sideLength):
    #This function draws a triangle
    for i in range(3):
        forward(sideLength)
        right(60)
```

A few things to note:

- The structure of the function definition looks a lot like a for-loop. There's an introduction line ending in a colon, and then an indented code block.
- The `def` keyword tells the computer you're defining a new function.
- The function's name, `draw_triangle`, comes right after `def`. You could call a function `x` but you'll regret it :)
- After the function's name is the list of arguments, surrounded by parentheses `(sideLength)`. Arguments are the things you need to tell the program before you can use the function. Think of arguments as questions the program might ask about what to do. For `draw_triangle`, the program wants to know "How long should the length of the sides be?" and you have to tell it the `sideLength`. Some functions won't have any arguments, so their arguments list will look like `()`. It depends how you design your functions.
- The first line of the function's code block should be a comment explaining what the function does.
- In the function's code block, you can use the arguments as variables.


{{< aside >}}
**Functions make your code simpler.** Instead of writing all the code for a triangle over and over, you can get it right once and put it in a function.

Once you have written a function, you must call it. Calling a function tells Python to run that block of code. Remember, order matters. **Code is read from top to bottom.** You cannot call a function before it has been written.

{{< /aside >}}



<br>

{{< checkpoint >}}

Look at the code below. Discuss the check-in questions in your group and answer the questions on your Google doc before moving on:


0.  What arguement does the hexagon function take?
0.  How is that arguement used in the hexagon function?
0.  What line of code is the hexagon function called?
0.  What line of code is the drawPattern function called?

```python
def hexagon(side_length):
   #Draws a hexagon"
   for i in range(6):
       forward(side_length)
       right(360//6)

def drawPattern():
    #Draws a hexagon pattern
    for each_side in range(6):
        pendown()
        hexagon(20)
        penup()
        forward(20)
        left(360 / 6)

drawPattern()
```

*This program will draw the below pattern.*
{{< figure src="images/courses/cs9/unit00/00_functions_hexagon.png" width="300px">}}

{{< /checkpoint >}}



---

## B. Writing Functions

{{< code-action >}} Create a new file in your `cs9/unit_00` directory called `lab_03.py`
and paste in this starter code:
{{< expand "Starter Code" >}}
```python
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


#################################

# B. WRITING CODE


def square():
    '''Draws a square with a side length of 20'''
    #YOUR CODE GOES HERE


def drawGrid():
    '''Draw a grid of squares using nested for loops.
    Use the function setup() to move the turtle.'''
    #YOUR CODE GOES HERE


#CALL DRAW GRID FUNCTION HERE


#Hides the turtle pen and keeps it open until key press
hideturtle()     
input("Press enter to end drawing...")
clearscreen()
```
{{< /expand >}}

Let's practice writing some functions. Fill in the code blocks for the functions in part **B**. If you succeed, you'll get the image below:



{{< figure src="images/courses/cs9/unit00/00_functions_grid.png" width="400px">}}

---

{{< checkpoint >}}

Discuss the check-in questions in your group and answer the questions on your Google doc before moving on:

0.  How did you decide where to call the `square()` function?
0.  How did you use loops to create a grid? 

{{< /checkpoint >}}

---

## C. Combining functions

When you want to draw something fancy, you need to break it down into smaller steps. Then you can write functions to do the smaller steps, and write more functions to combine small steps into bigger steps. This concept is called **decomposition**.

The code in part **C** illustrates this. If we want to draw an ice cream cone with scoops of ice cream like the one below, we can break it down into steps:

- Draw ice cream: `drawIceCream()`
    - Draw an ice cream cone: `cone()`
    - Draw scoops of ice cream: `iceCreamScoop(flavor,numScoops)`

{{< code-action >}} Your job is to fill in the functions: `drawIceCream()`, `cone()`, and `iceCreamScoop()`. Paste in this starter code below into your `lab_03.py` file:

{{< expand "Starter Code" >}}
```python
#################################

# C. COMBINING FUNCTIONS

def cone():
    "Draws an ice cream cone"
    # YOUR CODE HERE 


def iceCreamScoop(flavor, numScoops):
    '''Draws scoops of ice cream.
    Takes an ice cream flavor 
    and number of scoops as arguements'''
    # YOUR CODE HERE 

    

def drawIceCream():
    '''Draws an ice cream cone
    with the ice cream scoop on top.
    Use the function setup() to set the placement of the drawing.'''

#CALL DRAW ICE CREAM FUNCTION HERE

#Hides the turtle pen and keeps it open until key press
hideturtle()
input("Press enter to end program...")

```
{{< /expand >}}

A completed part **c** will look similar to the image below. The colors of the cone and ice cream scoops are up to you! 

{{< figure src="images/courses/cs9/unit00/00_functions_icecream.png" width="200px">}}


---

## Deliverables
For this lab, you should submit the following:
- The your `lab_04.py` file with the code you wrote for each of the parts
- Your Google Doc with responses to the checkpoint questions

