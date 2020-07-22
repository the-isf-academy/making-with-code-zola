---
title: Drawing Practice Homework
type: module
resources:
- name: Drawing Practice Figures
  src: images/courses/cs9/unit00/00_hw_drawing_practice.png
---

# Drawing Practice Homework

{{< devnote >}}
fix debugging strategies link
{{< /devnote >}}

{{< figure src="images/courses/cs9/unit00/00_hw_drawing_practice.png" width="400px" title="Drawing Practice Figures" >}}

Use Python's `turtle` library to draw the figures above.
In each case, the turtle should stop in the same place she started drawing, and she should be pointed in the same direction as she when started.
Try to get the correct form, but don't worry if the lengths are a little off.
You should use techniques from the {{< ref_module "lab_loops" >}}.
Hint: here's code for drawing a hexagon:

```python
    from turtle import *
    for each_side in range(6):
        forward(50)
        right(60)
```
## Notes

- Try drawing these by hand. Notice when you are repeating the same pattern.
- Get part of the pattern working first, then figure out how to repeat it.
- If you get stuck, try using our [debugging strategies]().

## Starter code

Save this as `unit_00/homework_03.py`.

```python
    # Unit 0 Lesson 3 Solution
    # Author: Chris Proctor

    from turtle import *

    # This is a function. It teaches the computer a new command.
    # You'll learn how to use functions soon.
    def setup(x, y):
        "Sets up the turtle, ready to draw, at the given coordinates"
        penup()
        goto(x, y)
        pendown()
        setheading(0)

    # Figure 0
    setup(-100, 100)
    # YOUR CODE HERE

    # Figure 1
    setup(100, 100)
    # YOUR CODE HERE    

    # Figure 2
    setup(-100, -100)
    # YOUR CODE HERE

    # Figure 3
    setup(100, -100)
    # YOUR CODE HERE

    input("Press enter...")
```

## Deliverables
- A Python file called `homework_03.py` submitted.
- The program should draw four figures, roughly matching the image above.
- Each figure should use a list (so you don't have to repeat the same code over and over).
- The turtle should end each figure in the same position and orientation as she started.
