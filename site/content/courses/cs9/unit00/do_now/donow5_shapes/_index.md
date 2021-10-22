---
title: 5. Shapes
type: checkup
---

# Shapes

{{< code-action "Create a new file in your" >}} `do_now` **folder.**
```shell
cd Desktop/cs9/unit_00/
cd do_now
atom donow5.py
```


{{< code-action "The code block below is inefficient. Each shape (square, pentagon, hexagon, heptagon) has its own function. Replace these 4 functions with just 1 function that can draw any shape." >}} Start by copying and pasting the code into your `donow5.py` file.
>  Remember that once you've written the new function, you will also need to change the `while` loop so that it calls the new function instead of the old ones.
>


```python
#############
# donow5.py
#############

from turtle import *


def square():
    for i in range(4):
        forward(100)
        right(360/4)

def pentagon():
    for i in range(5):
        forward(100)
        right(360/5)

def hexagon():
    for i in range(6):
        forward(100)
        right(360/6)

def heptagon():
    for i in range(7):
        forward(100)
        right(360/7)

speed(10)
while True:
    drawing = input("What would you like me to draw? ")
    if drawing == "square":
        square()
    elif drawing == "pentagon":
        pentagon()
    elif drawing == "hexagon":
        hexagon()
    elif drawing == "heptagon":
        heptagon()
    elif drawing == "quit":
        break
    else:
        print("Sorry, I don't know how to draw that...")

```
