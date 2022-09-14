---
title: 6. Functions
type: lab
resources:
- name: test_part_b() output
  src: images/courses/cs9/unit00/00_functions_fig_b.png  
- name: draw_forest(10) output
  src: images/courses/cs9/unit00/00_functions_forest.png

slug: lab_functions
repo_url: https://github.com/the-isf-academy/lab_functions.git
init_action: clone
# draft: true
---
# Functions Lab

In this lab, we will learn how to create and call functions. Functions are blocks of code that are reusable throughout a program. You've already encountered functions such as `print()`, which is a function built into Python.


---

## [0] Set up

{{< code-action "Start by opening the Terminal cloning this lab onto your laptop." >}} As a reminder, we will run this command at the start of each lab.
```shell
mwc update
```
{{< code-action "In the Terminal, type the following command to open the lab folder." >}}
```shell
cd ~/desktop/making_with_code/cs9/unit00_drawing/lab_functions
```

{{< code-action "Enter the Poetry Shell to start the lab." >}} As a reminder, we will run this command at the start of each lab, but only when we are inside a lab folder.
```shell
poetry shell
```
{{< aside "Exiting the poetry shell" >}}
When you want to exit the shell, you can type `exit` or `^D`
{{< /aside >}}

{{< code-action "Take a look at the files inside with:" >}} `ls`
- `guessing_game.py`
- `hailstone_sequence.py`

---


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



Often times we want to reuse a code block in different sections of a program. `Functions` allow for code reuse without needing to copy and paste code blocks. **Here is a code block with a function definition and a function call:**

```python {linenos=table}
def draw_triangle(side_length):
    #This function draws a triangle
    for i in range(3):
        forward(side_length)
        left(120)

draw_triangle(200)
```

> A few things to note:
>
> - `line 1`
>   - `def` defines a new function called `draw_triangle()`
>   - it takes on parameter, or arguement, called `side_length`
> - `line 4` 
>   - `side_length` is used as a variable
>   - you can use function's parameters inside the function as variables
> - `line 7`
>   - `draw_triangle(200)` calls the function with a `side_length` of `200`
>   - Once you have written a function, you must call it to use it.

{{< expand "A few more tips on functions..." >}}
- Whenever a code block is indented, there's always a line introducing it. This line always ends with a colon.
- The way you indent matters. **Always use the tab key to indent.**
- When you're done with a code block, just stop indenting.

- After the function's name is the list of arguments, surrounded by parentheses `(side_length)`. Arguments, or parameters, are the things you need to tell the program before you can use the function. Think of arguments as questions the program might ask about what to do. For `draw_triangle`, the program wants to know "How long should the length of the sides be?" and you have to tell it the `side_length`. Some functions won't have any arguments, so their parameters list will look like `()`. It depends how you design your functions.
- The first line of the function's code block should be a comment explaining what the function does.
- In the function's code block, you can use the arguments as variables.

{{< /expand >}}



{{< aside >}}
**Functions make your code simpler.** Instead of writing all the code for a triangle over and over, you can get it right once and put it in a function.

**Once you have written a function, you must call it.** Calling a function tells Python to run that block of code. Remember, order matters. **Code is read from top to bottom.** You cannot call a function before it has been written.

{{< /aside >}}

---

### [Editing a Function]

{{< code-action "Let's start by running" >}} `draw_triangle.py`
```shell
python draw_triangle.py
```

{{< figure src="images/courses/cs9/unit00/00_functions_0.png" width="300px">}}


{{< code-action "Now, let's open the file:" >}} 
```shell
atom draw_triangle.py
```
Notice how it calls the `draw_triangle()` function with a `side_length` of `200`.

{{< code-action "Experiment with editing the paramter and then re-running the program." >}} For example, change `200` to a `500`.

---

### [Writing  a Function]

Now that you've had some practice editing a function, let's write a new one. 

{{< code-action "Open the file:" >}} `draw_hexagon.py`
```shell
atom draw_hexagon.py`
```

{{< code-action "Write a function that draws a hexagon with any side_length." >}} You will need to:

0. write the function `draw_hexagon()`
0. call the function `draw_hexagon()` below the function definition

*Your finished drawing should look something like this:*
{{< figure src="images/courses/cs9/unit00/00_functions_1.png" width="300px">}}


---


## [1] Combining functions

**When you want to draw something fancy, you need to break it down into smaller steps.** Then you can write functions to do the smaller steps, and write more functions to combine small steps into bigger steps. This concept is called **decomposition**.

The code in this lab illustrates this. If we want to draw an ice cream cone with scoops of ice cream, we can break it down into steps:

- Draw ice cream: `draw_icecream(num_scoops)`
    - Draw an ice cream cone: `cone()`
    - Draw a scoop of ice cream: `icecream_scoop()`
    - Move the turtle between scoops: `setup(x,y)`


### [Draw the Ice Cream]

{{< code-action "Finish the following functions to draw ice cream: " >}}
- `draw_icecream(num_scoops)`
- `cone()`
- `icecream_scoop()`

Your finished drawing will look similar to the image below. The colors of the cone and ice cream scoops are up to you!

{{< figure src="images/courses/cs9/unit00/00_functions_icecream.png" width="200px">}}


{{<aside "FYI: How to Fill a Shape with Color and More!" >}}
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



---

## [2] Looping Functions

Let's practice writing some more functions. Our aim is to create a grid of squares. 

{{< figure src="images/courses/cs9/unit00/lab_06_functions_02.png" width="50%">}}

This is a complex problem, and thus we should use the practice of **decompsition** to break it down into smaller steps. 

- **Step 1:** Drawing one square
- **Step 2:** Drawing one line of squares
- **Step 3:** Drawing a grid of squares 

### [Set up]

{{< code-action "Create a new file" >}} called `grid.py` in your `lab_06_functions` folder. Copy and paste the code below into your file.

```python
#################################
# Unit 0 Lab 6
# Author: Your Name
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

def square(square_size):
    '''Draws a square using `square_size` as the length'''
    #YOUR CODE GOES HERE


#Keeps the drawing window open until key press  
input("Press return to end drawing...")
```

### [Step 1]

{{< code-action "Fill in the" >}} `square(square_size)` function. It should draw one square of any size. 

{{< figure src="images/courses/cs9/unit00/lab_06_functions_00.png" width="25%">}}


{{< checkpoint >}}

Before moving on, test your `square(square_size)` function. 

In your notebook answer the following question:
- How do you know your function will draw a square of any size?

{{< /checkpoint >}}

### [Step 2]

{{< code-action "Copy and paste the following code block below the " >}} `square(square_size)` function.

```python
def draw_grid(square_size, gap_size):
    '''Draws a grid of squares. 
    Uses `square_size` for the size of the square
    and `gap_size` for the size of the gap inbetween each square.
    Uses the function setup() to set the placement of the scoops.'''


```

{{< code-action "Implement the STEP 2 functionality in the" >}} `draw_grid(square_size, gap_size)` function. Draw one line of squares the length of `square_size` with gap the size of `gap_size`.

{{< figure src="images/courses/cs9/unit00/lab_06_functions_01.png" width="50%">}}


{{< checkpoint >}}

Before moving on, test your `draw_grid(square_size, gap_size)` function. 

In your notebook answer the following question:
- How do you know your function will draw a line of squares of any `square_size` and any `grid_size`?

{{< /checkpoint >}}

### [Step 3]

{{< code-action "Implement the STEP 3 functionality in the" >}} `draw_grid(square_size, gap_size)` function. 

{{< figure src="images/courses/cs9/unit00/lab_06_functions_02.png" width="50%">}}

{{< checkpoint >}}

Before moving on, test your `draw_grid(square_size, gap_size)` function. 

In your notebook answer the following question:
- How do you know your function will draw a grid of squares of any `square_size` and any `grid_size`?

{{< /checkpoint >}}

---

## [3] Deliverables

{{< deliverables  >}}

**Once you've successfully completed the square pattern be sure to fill out [this Google form](https://docs.google.com/forms/d/e/1FAIpQLSdghFADPT-K94LCT6QS9V_L626bYfoJXDUvYiPIGLeHrUopkA/viewform?usp=sf_link)**.


{{< /deliverables >}}

---
## [4] Extension

### [Ice Cream Parlor]

Let's return to `ice_cream.py`. 

Right now, both the color of the ice cream and the number of scoops are pre-determined or hard-coded. If you wanted to change the color or number of scoops, you would have to go back into the code and change it yourself. 

{{< code-action "Expand the functionality of this program to simulate an ice cream parlor."  >}} The user should be able to choose the flavor of the ice-cream and the number of scoops.

{{<aside "Hints" >}}

Consider the following:
- How will you implement the functionality of a `flavor` that is not hard-coded?
- How will you include user input?
- How will you translate the flavor "chocolate" to the color "brown?

{{</aside>}}

Here is an example interaction:

```shell
python3 ice_cream.py

--- Welcome to the ISF ice cream parlor ---

What flavor would you like?
   > Select a flavor (chocolate, strawberry, vanilla): chocolate
How many scoops would you like? 
   > Select number of scoops (max 3): 3

--- Enjoy your ice cream! Please come again! ---

[Press any key to exit]
```

{{< figure src="images/courses/cs9/unit00/lab_06_functions_03.png" width="25%">}}


### [Custom Grid]

Let's return to `grid.py`.

{{< code-action "Expand the functionality of this program so the user can customize the following:"  >}} 
- number of rows
- number of columns
- color palette 


Here is an example interaction:

```shell
python3 grid.py

--- PATERN GENERATOR ---

How many rows?
   > Enter a number: 5
How many columns?
   > Enter a number: 3
Pick a primary color.
   > Choose a color (darkseagreen, coral, deeppink): darkseagreen
Pick a secondary color.
   > Choose a color (darkred, , cyan, cadetblue): coral

[Press any key to exit]
```

{{< figure src="images/courses/cs9/unit00/lab_06_functions_04.png" width="50%">}}
