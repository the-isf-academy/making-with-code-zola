---
title: 3. Loops and Conditionals
type: labs
---

# Loops and Conditionals
In this lab, we'll continue our exploration of loops and introduce a new concept that will
allow us to make even more interesting drawings: conditionals.

{{< include_resource "resource_conditionals" >}}

## Responding to user input

```python
# CONDITIONALS 
speed(10)
drawing = input("What would you like me to draw? ")
size = int(input("How big should I draw it? "))
if drawing == "square":
    for i in range(4):
        forward(size)
        right(90)
else:
    print("Sorry, I don't know how to draw that...")
```

### Add a  shape

### while true/break

### Clear

## Modulo minilesson

## rainbow

```python
# RAINBOW
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

## While mini-lesson

## Hailstone

```python
# HAILSTONE
num = int(input("What number should I calculate the hailstone sequence of? "))
```

## Drawing Hailstone

