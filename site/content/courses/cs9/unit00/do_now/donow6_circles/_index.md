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
 The code block below has a bug in it. It should be drawing 4 circles, one of each color. However, right now one of the circles is black.

{{< code-action "In your `donow6.py` file, fix the bug so that all the circles are colorful." >}}



```python
#############
# donow6.py
#############

def color_circles(color1, color2, color3, color4):
    speed(0)

    for i in range(4):
        if i == 1:
            color(color1)

        if i == 2:
            color(color2)

        if i == 3:
            color(color3)

        if i == 4:
            color(color4)


        circle(100)
        penup()
        forward(20)
        pendown()
        right(360/4)

color_circles('red','blue','purple','green')
input()


```
