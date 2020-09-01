---
title: 3. Loops and Conditionals
type: labs
<<<<<<< HEAD

=======
>>>>>>> 04f571b5a57496cf6ec4eac0a20a1af0dda47094
---

# Loops and Conditionals
In this lab, we'll continue our exploration of loops and introduce a new concept that will
allow us to make even more interesting drawings: conditionals.

## Intro to conditionals
{{< include_resource "resource_conditionals" >}}

## A. Responding to user input
One way to use conditionals in our drawings is to use them to respond to user input.

{{< code-action >}} Create a new file in your `cs9/unit_00` directory called `lab_03.py`
and paste in this starter code:

```python
# A. USER INPUT
from turtle import *
speed(10)
while True:
    drawing = input("What would you like me to draw? ")
    size = int(input("How big should I draw it? "))
    if drawing == "square":
        for i in range(4):
            forward(size)
            right(90)
    elif drawing == "quit":
        break
    else:
        print("Sorry, I don't know how to draw that...")
```

{{< code-action >}} Run this program to see how it uses a conditional based on user input.

This program has a lot of potential, but so far it can only generate one drawing.

{{< code-action >}} Add at least two more branches to the conditional so that the program can
draw more shapes. An `elif` statement will probably be useful here.

{{< checkpoint >}}
Answer the following check-in questions on your group's Google doc before moving on:

0. What is the difference between `else` and `elif` statements in a conditional?
0. When writing a conditional, what kinds of things can you compare? Can you compare different
types of things to each other?
{{< /checkpoint >}}

## Modulo
{{< include_resource "resource_modulo" >}}

## B. Rainbow
Conditionals can also be paired with the modulo operator to cause your code to run in repeated
patterns.

{{< code-action >}} Copy the code below into your `lab_03.py` file and run it to see what it does,

```python
# B. RAINBOW
speed(10)
for i in range(5):
    color("red")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("orange")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("yellow")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("green")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("blue")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("purple")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("violet")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()

input()
```

This code is really long. However, there is a pattern to the rainbow that we could use
to simplify the code: the rainbow has 7 colors that repeat every time the loop runs for 7
iterations.

{{< code-action >}} Simplify this code using a conditional and the modulo operator.

{{< checkpoint >}}
Answer the following check-in questions on your group's Google doc before moving on:

0. How would you describe the modulo operator to a friend who has never heard of it before?
0. What other situations do you think the modulo operator would be useful in?
{{< /checkpoint >}}

## While loops

{{< include_resource "resource_while_loops" >}}

## C. Hailstone sequence
In the last part of this lab, you will be exploring a special sequence known as the
hailstone sequence. This sequence results from the following rules (known as the Collatz
conjecture):

- take any positive number `n`
- find the next term of the sequence using the following rules:
    - if `n` is even, the next term is `n/2`
    - if `n` is odd, the next term is `n*3+1`
- repeat until `n = 1`

The conjecture states that no matter the starting value of `n`, the sequences will always
reach 1.

{{< write-action >}} Try this out: pick a number and perform the calculations. Can you find a
number that doesn't reach one?

This sequence is interesting because though no number has ever been found that doesn't reach 1,
the Collatz conjecture has never been proven. **This is an unsolved problem in mathematics!**

### C.0 Calculating hailstone sequences

#### Pseudo-code
This is another alogrithm which will require pseudo-code to figure out.
{{< write-action >}} Write out pseudo-code to plan the logic of this program.

Here are some things to consider:
- This program will require a loop. What kind of loop do you think is best? Remember that
for loops run for a definite number of times and while loops run until a condition is met.
- You will need to determine if each term is odd or even. What are some characteristics
of even numbers that will help you determine if a number is even?
- In addition to calculating each term, you should also count how many steps it takes to
reach zero and report this number at the end. You should use a `count` variable
to track the number of steps.

#### Code
Once you've completed your pseudo-code, you can translate it into Python code.

{{< code-action >}} Use the following to get started:

```python
# HAILSTONE
num = int(input("What number should I calculate the hailstone sequence of? "))
count = 0

# Put your code here

print("Took " + str(count) + " steps to reach 1.")
```

{{< aside >}}
When you are multiplying or dividing the term during each step of the algorithm, you
will need to put your operation inside a `int()` statement. For example, if you want
to divide a number by two, use:

```python
num = int(num/2)
```

This is necessary because Python stores integers and decimal numbers in different ways.
However, in this program you always want to use integers. We'll talk about this more in
the next unit.
{{< /aside >}}

{{< checkpoint >}}
Answer the following check-in questions on your group's Google doc before moving on:

0. What kind of loop did you choose to write the hailstone sequence algorithm? Why did you choose
this kind of loop?
0. Why do you think the Collatz conjecture is so hard to prove for all positive integers?
{{< /checkpoint >}}

### C.1 Drawing Hailstone
The sequences formed are known as hailstone sequences, because the terms move up
and down but ultimately reach 0 like hailstones gaining layers of ice in a cloud.

{{< figure src="images/courses/cs9/unit00/00_conditionals_hailstone_cloud.png" width="100%" title="Hailstones froming in a cloud" >}}

This pattern can lead to some interesting visualizations of hailstone sequences.

You can visualize the terms in a sequence starting with a specific number:
{{< figure src="images/courses/cs9/unit00/00_conditionals_hailstone_terms.png" width="100%" title="Terms in hailstone sequence starting at 590" >}}

Or you can visualize the number of steps it takes to reach one from a set of integers:
{{< figure src="images/courses/cs9/unit00/00_conditionals_hailstone_steps.png" width="100%" title="Steps to reach one in hailstone sequence as radii of half circles for integers 1-100" >}}

{{< code-action >}} Use your hailstone sequence code from part C.0 to create a visualization fo the
hailstone sequence using Turtle.

## Deliverables
For this lab, you should submit the following:
- The your `lab_03.py` file with the code you wrote for each of the parts
- Your Google Doc with responses to the checkpoint questions
