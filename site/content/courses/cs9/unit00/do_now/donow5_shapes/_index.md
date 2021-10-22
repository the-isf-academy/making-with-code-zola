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
 The code block below is inefficient. Each shape (square, pentagon, hexagon, heptagon) has its own function.

{{< code-action "In your `donow5.py` file, write a function that can draw any shape." >}}
>  Consider: will your new function need parameter?
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

```
