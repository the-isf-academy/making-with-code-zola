---
title: 6. Circles
type: checkup
#draft: false
---

# Circles

{{< code-action "Create a new file in your" >}} `do_now` **folder.**
```shell
cd Desktop/cs9/unit_00/
cd do_now
atom donow6.py
```
 The code block below has a bug in it. It should be drawing 6 circles, one of each color. Right now the purple circle isn't appearing.

{{< code-action "In your `donow6.py` file, fix the bug so that the purple circle appears." >}}



```python
#############
# donow6.py
#############

from turtle import *

num_circles = 6
speed(0)

for i in range(num_circles):
    if i == 1:
        color("red")
        circle(10)
    if i == 2:
        color("orange")
        circle(10)
    if i == 3:
        color("yellow")
        circle(10)
    if i == 4:
        color("green")
        circle(10)
    if i == 5:
        color("blue")
        circle(10)
    if i == 6:
        color("purple")
        circle(10)
    penup()
    forward(20)
    pendown()
    right(360/num_circles)

input()


```
