---
title: 3. Loops
type: lab
# draft: true

---

# Loops Lab
In this lab, we will learn how to make the computer do the same instruction over and over. 

In Python, when you want to run the same code multiple times, we use loops.
If you have used Scratch before, you have seen loops before:

{{< figure src="images/courses/cs9/unit00/00_loops_scratch_loop.png" width="200px" title="Scratch loop" >}}

How does a loop work in python? Let's see.

## [0] How to loop

{{< code-action "Create new folder in your cs9/unit_00 folder called" >}} `lab_03_loops`. **In the** `lab_03_loops` **folder, create a new file called** `loops_intro.py`. **Copy and paste the code below into your file.**

```python
######################
# Unit 0 Lab 3
# Author: Your Name
#######################

from turtle import *

# -- [0] HOW TO LOOP --
# [PART A: CALCULATIONS]
print("-- Calculations --")
for i in range(10):
    print(i)

# [PART B: SQUARING NUMBERS]
# YOUR CODE GOES HERE

# [PART C: LOOPING A SQUARE]
# YOUR CODE GOES HERE
```

### [Part A: Calculations]
{{< code-action "Run your program and see what gets output." >}} 

This loop runs 10 times, repeating everything indented to the right of the `for i in range(10):` line.
`i` is a variable that gets incremented by one every time the loop runs.

{{< code-action "Edit the code to make the loop run a different number of times" >}} Maybe 5 or 14.
Can you figure out how to do it?

<hr>

### [Part B: Squaring Numbers]

{{< code-action "Using a loop, print the square of numbers 0-12." >}} Put your code under "#[PART B: SQUARING NUMBERS]"

{{< aside "FYI: Math in Python" >}}
One feature of the Python language is that it understands math equations. 

For example,
```python
print(1+1)
```

Will output,
```shell
2
```

And, 
```python
print(10/2)
```

Will output,
```shell
5
```

It also follow the convention of order of operations
```python
(3*2)+(5+5)
```

Will output,
```shell
16
```
{{< /aside >}}

Your loop output should look like this:
```shell
0
1
4
9
16
25
36
49
64
81
100
121
```

{{< aside "FYI: Commenting out code" >}}
If you don't want code to be executed when you run a program, you can comment it
out by placing `#` at the beginning of the line.

If you don't wan't to run the code from 'Part A', just
comment it out.
{{< /aside >}}

<hr>

### [Part C: Looping a Square]

Take a look at the code we've been using to draw a square:

```python
forward(100)
right(90)
forward(100)
right(90)
forward(100)
right(90)
forward(100)
right(90)
```

Pretty repetitive, right?

{{< code-action "Under 'PART C: LOOPING A SQUARE', use a loop to draw a square to avoid repeating the same code over and over again." >}}

{{< checkpoint >}}
Answer the following check-in questions in your notebook before moving on:

0. What is a loop?
0. How do you put code into a loop?
0. What changes over each iteration of a loop? What stays the same?
{{< /checkpoint >}}

<hr>

## [1] Geometric sequences

Loops are particularly useful when we need to do things over time. To see this, **let's write a program that uses a loop to list out the first 10 terms in any geometric sequence.**

{{< aside "FYI: Sequences" >}}
Sequences are ordered collections of numbers that have a pattern to determine
which numbers appear in the sequence. For example, `2, 4, 6, 8, 10,...` is a
sequence where each number 2 more than the previous number.

**Geometric sequences are sequences where there is a common ratio between each
number in the sequence.** For example, `3, 9, 27, 81,...` is a geometric sequence
where each number is 3 times the number before it (making the common ratio 3).
{{< /aside >}}

Here is an example of what the program will output when run:
```shell
$ python3 geometricsequences.py
What should the ratio of the sequence be? 4
4
16
64
256
1024
4096
16384
65536
262144
1048576
```

### [Pseudocode]
To get started, think through the *pseudo-code* of what we want this program to do. **Pseudocode** is an outline of the program we'll ultimately write where we don't worry about using Python syntax.

{{< checkpoint >}}
**In your notebook write the psuedocode to list the first 10 numbers of any geometric sequence.**

Here are some things to consider:
- You will use a loop to calculate each term in the sequence. What is the formula
you will use at each step in the loop to calculate the term?
- You will need to know the previous term to calculate the current term. How will
you keep track of this?
{{< /checkpoint >}}



### [Code]

{{< code-action "After you are confident your pseduocode has the correct logic, translate it into python code." >}} Create a new file for your geometric sequence program called `geometric_sequence.py`.

<hr>

## [2] Fibonacci Sequence
Let's explore another sequence, the Fibonacci sequence. This sequence has all kinds
of interesting properties.

**We're going to write an algorithm to print out numbers in the Fibonnaci sequence.**

The Fibbonacci sequence begins with two numbers, `0` and `1`. Each subsequent number in the sequence is calucated by finding the sum of the two numbers that precede it. 

{{< write-action "In your notebook, calculate the first 10 numbers of the Fibbonacci sequence and show your work." >}}


Here is an example of what the program will output when run:
```shell
$ python3 fibonacci_sequence.py
How many numbers of the Fibonacci sequence would you like to output? 3
1
1
2
```

{{< look-action >}} Watch this video to learn about how the Fibonacci sequence appears in
nature:
{{< youtube id="ahXIMUkSXX0" >}}

### [Pseudocode]

{{< checkpoint >}}
In your notebook,

0. Write the pseudocode for the Fibonacci sequence algorithm. 
0. Calculate the first 5 numbers of the Fibonacci sequence by exclusively following your pseudocode. 

Be sure to check-in with a teacher before moving on. 

{{< /checkpoint >}}


### [Code]
{{< code-action "After you are confident your pseduocode has the correct logic, translate it into python code." >}}  Create a new file for your fibonacci sequence program called `fibonacci_sequence.py`.

## [3] Deliverables

{{< deliverables "Please submit your lab by copying your files into your CS9 Google Drive folder and answering the prompt." >}}

**Files:**
- `loops_intro.py`
- `geometric_sequence.py`
- `fibonacci_sequence.py`

**Prompt:**

Describe a moment where your code didn't do as intended. How did you debug it? 
{{< /deliverables >}}

<hr>

## [4] Extension: Visualizing Fibonacci

Let's use the code you wrote to calculate Fibonacci sequences to make pattern
drawings inspired by flowers and pinecones.

{{< figure src="images/courses/cs9/unit00/00_variables_pinecone.png" title="Fibonacci drawing" >}}

### [One spiral]
First, use your Fibonacci code to draw a single spiral. You can do this by drawing a
line for each number in the Fibonacci sequence and connecting the lines at a standard angle.

{{< code-action "Incorporate the Turtle drawing functionality into your" >}} `fibonacci_sequence.py` file.

The Turtle should draw something like this:

{{< figure src="images/courses/cs9/unit00/00_variables_spiral.png" title="Fibonacci spiral" >}}

### [Multiple spirals]
{{< code-action "Loop the drawing code to draw multiple spirals originating from the center." >}} 

Now, the Turtle should draw something like this:

{{< figure src="images/courses/cs9/unit00/00_variables_vortex.png" title="Many spirals" >}}

{{< aside "FYI: Moving the Turtle" >}}
You can return your turtle to the center of the window using `goto(0, 0)`. You can also use `penup()` and `pendown()` to keep the turtle from drawing as it returns to the
center.
{{< /aside >}}

### [Clockwise and counterclockwise]
To get a pinecone or flower effect like the video above described, you'll need to spiral clockwise
and countercloackwise.

{{< code-action "Repeat your spiral code, changing it to make your spirals turn in the other direction." >}}

Feel free to add colors and personalize the visualization however you would like! 

{{< code-action "Be sure to update your file in your Hapara drive!" >}}
