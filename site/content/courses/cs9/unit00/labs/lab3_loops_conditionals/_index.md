---
title: 3. Loops and Conditionals
type: labs
---

# Loops and Conditionals
In this lab, we'll continue our exploration of loops and introduce a new concept that will
allow us to make even more interesting drawings: conditionals.

{{< include_resource "resource_conditionals" >}}

## A. Responding to user input
One way to use conditionals in our drawings is to use them to respond to user input.

{{< code-action >}} Create a new file in your `cs9/unit_00` directory called `lab_03.py`
and paste in this starter code:

```python
# A. USER INPUT
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
```

This code is really long. However, there is a pattern to the rainbow that we could use
to simplify the code: the rainbow has 7 colors that repeat every time the loop runs for 7
iterations.

{{< code-action >}} Simplify this code using a conditional and the modulo operator.

{{< include_resource "resource_while_loops" >}}

## C. Hailstone sequence

### C.0 Calculating hailstone sequences

```python
# HAILSTONE
num = int(input("What number should I calculate the hailstone sequence of? "))
```

### C.1 Drawing Hailstone

