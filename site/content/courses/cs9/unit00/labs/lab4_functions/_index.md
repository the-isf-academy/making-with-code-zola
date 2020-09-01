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

{{< devnote >}}

{{< /devnote >}}

## Starter code
Create a new file called `lab_04.py` in atom (This should be at `~/Desktop/cs9/unit_00/lab_04.py`.) You'll be turning in this file at the end of the lab. Copy this starter code:

{{< expand "Starter code for functions lab" >}}

```python
# Unit 0 Lab 4
# Author: PUT YOUR NAME HERE
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

# A. CODE BLOCKS


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


#################################
```

{{< /expand >}}

## A. Code blocks
Before we can talk about functions, we need to talk about code blocks. A **code block** is one or more lines of code. Here's one:

```python
    forward(100)
    right(90)
```

Sometimes we want to talk about how many times a code block should run, or whether it should run at all.
Consider this code, which will draw a square:

```python
    for each_side in range(4):
        forward(100)
        right(90)
```

We have the same code block, but now it's indented under the condition `for each_side in range(4):`. This means
the code block should run once for each item in the range. A few things to note:

- Whenever a code block is indented, there's always a line introducing it. This line always ends with a colon.
- The way you indent matters. **Always use the tab key to indent.**
- When you're done with a code block, just stop indenting.

There are also `if` code blocks, which say the code should only run if some condition is true. (And you can
add an `else` code block for what to do if the condition is not true.)

```python
    if 1 + 1 == 3:
        print("Your computer has a serious problem.")
    else:
        print("All is well.")
```

Now look at Part A in the starter code. There is a code block inside another code block (a double-indent). Run the code. Work with your table group to figure out what part A does and how it works.

#### Checkpoint: When you are sure **everyone at your table** understands code blocks, and can explain Part A, raise your hand.

---

## B. Functions

OK, that's enough guessing for now. Set `ASK_FOR_PASSWORD = False` so that the program no longer asks for your password. Also, set `TEST_PART_B = True`.

When you define a function, you are giving a name (`setup`) to a code block. Then you can tell the
computer to run the code block by calling it by its name (`setup(100, 200)`). Think of it as teaching a new
word to the computer. It lets you talk about new ideas. You already saw a function, in today's homework:

```python
    def setup(x, y):
        "Sets up the turtle, ready to draw, at the given coordinates"
        penup()
        goto(x, y)
        pendown()
        setheading(0)
```

A few things to note:

- The structure of the function definition looks a lot like a for-loop. There's an introduction line ending in a colon, and then an indented code block.
- The `def` keyword tells the computer you're defining a new function.
- The function's name, `setup`, comes right after `def`. Here are some examples of good function names: `draw_circle`, `draw_house`, `draw_background_with_clouds`. You could call a function `x` but you'll regret it :)
- After the function's name is the list of arguments, surrounded by parentheses `(x, y)`. Arguments are the things you need to tell the program before you can use the function. Think of arguments as questions the program might ask about what to do. For `setup`, the program wants to know "Where should we set up?" and you have to tell it the `x`- and `y`-coordinates. Some functions won't have any arguments, so their arguments list will look like `()`. It depends how you design your functions.
- The first line of the function's code block should be a string explaining what the function does.
- In the function's code block, you can use the arguments as variables.

One reason to write functions is to make your code simpler. Instead of writing all the code for a square over and over, you can get it right once and put it in a function.

Let's practice writing some functions. Fill in the code blocks for the functions in part **B**. If you succeed, you'll get the image below:


{{< figure src="images/courses/cs9/unit00/00_functions_fig_b.png" width="400px" title="test_part_b() output" >}}

---

Set `TEST_PART_B = False` and `TEST_PART_C = True`.

#### Checkpoint: When you are sure **everyone at your table** understands and can explain Part B, raise your hand.


---

## C. Combining functions

When you want to draw something fancy, you need to break it down into smaller steps. Then you can write functions to do the smaller steps, and write more functions to combine small steps into bigger steps. The code in part **C** illustrates this. If we want to draw a random forest like the one below, we can break it down into steps:

- Draw a forest
    - Draw a tree
        - Draw branches (we'll use `triangle`)
        - Draw the trunk (we'll use `rectangle`)
        - Move around (we'll use `fly`)

Your job is to write `rectangle` and `fly`.

{{< figure src="images/courses/cs9/unit00/00_functions_forest.png" width="400px" title="draw_forest(10) output" >}}

---

## Deliverables
- Each student should turn in `lab_03.py` at the end of class.
