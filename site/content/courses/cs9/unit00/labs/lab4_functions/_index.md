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
Create a new file called `lab_03.py` in atom (This should be at `~/Desktop/cs9/unit_00/lab_03.py`.) You'll be turning in this file at the end of the lab. Copy this starter code:

{{< expand "Starter code for functions lab" >}}

```python
    # Unit 0 Lab 3
    # Author: Your Name

    from turtle import *
    from random import *

    # These constants affect how the program works, so we'll list them all at the top
    ASK_FOR_PASSWORD = True
    PASSWORD = "noodles"
    TEST_PART_B = False
    TEST_PART_C = False

    # A. CODE BLOCKS

    if ASK_FOR_PASSWORD:
        guess = input("What's the password? ")
        if guess == PASSWORD:
            print("Yesssss!!!!")
            print("Noodles are delicious.")
            raise NotImplementedError("I'm going to go eat some noodles.")
        else:
            raise ValueError("Wrong password! Now I will crash the program.")

    # B. FUNCTIONS

    def setup(x, y):
        "Sets up the turtle, ready to draw, at the given coordinates"
        penup()
        goto(x, y)
        pendown()
        setheading(0)

    def triangle(side_length):
        "Draws a triangle"
        for each_side in range(3):
            forward(side_length)
            right(120)

    def square(side_length):
        "Draws a square"
        # YOUR CODE HERE (B1)


    def pentagon(side_length):
        "Draws a pentagon"
        # YOUR CODE HERE (B2)


    def hexagon(side_length):
        "Draws a hexagon"
        # YOUR CODE HERE (B3)


    def polygon(side_length, number_of_sides):
        "Draws a polygon with any number of sides"
        # YOUR CODE HERE (B4)


    def test_part_b():
        print("Testing out your functions from part B")
        speed(0)
        for x in range(0, 50, 10):
            for y in range(0, 50, 10):
                setup(x, y)
                square(8)
        setup(-70, -60)
        for each_side in range(5):
            pendown()
            pentagon(20)
            penup()
            forward(20)
            left(360 / 5)
        setup(-70, 60)
        for each_side in range(6):
            pendown()
            hexagon(20)
            penup()
            forward(20)
            left(360 / 6)
        setup(100, 50)
        for n in range(3, 10):
            polygon(30, n)
        input("Press enter to continue...")

    if TEST_PART_B:
        test_part_b()

    # C. COMBINING FUNCTIONS

    def rectangle(width, height):
        "Draws a rectangle, starting with the width and turning to the right"
        # YOUR CODE HERE (C1)


    def fly(distance):
        "Picks up the pen, moves, and then puts the pen down again"
        # YOUR CODE HERE (C2)


    def draw_tree(size):
        "Draws a tree, using a rectangle and three triangles. Starts and ends at the top of the tree"
        branch_sizes = [size * 1.2, size, size * 0.8]
        trunk_width = size * 0.2
        fillcolor("brown")
        right(90)
        fly(-trunk_width/2)
        begin_fill()
        rectangle(trunk_width, branch_sizes[0]*1.3)
        end_fill()
        fly(trunk_width/2)
        left(90)
        fillcolor("green")
        for branch_size in branch_sizes:
            right(150)
            begin_fill()
            triangle(branch_size)
            end_fill()
            left(150)
            fly(branch_size / 2)

    def draw_forest(number_of_trees):
        "Draws a forest of trees"
        print("Testing part C")
        speed(4)
        tree_y_positions = [randint(100, 200) for i in range(number_of_trees)]
        tree_y_positions = reversed(sorted(tree_y_positions))
        for y in tree_y_positions:
            x = randint(-200, 200)
            tree_size = 250 - y
            setup(x, y)
            left(90)
            draw_tree(tree_size)
        input("Press enter to continue...")

    if TEST_PART_C:
        draw_forest(10)
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
