---
title: Functions Practice Homework
type: module
resources:
- name: Functions Practice Figures
  src: images/courses/cs9/unit00/00_hw_functions_practice.png
---

# Practice Writing Functions

{{< figure src="images/courses/cs9/unit00/00_hw_functions_practice.png" width="400px" title="Functions Practice Figures" >}}

If we want to draw more complicated pictures, we'll need to teach the computer more complicated
commands. The starter code below defines a bunch of functions. It's your job to make them work.
If you implement the functions correctly, the starter code will generate a picture that matches the
one above.

Here are a couple of conventions we'll follow when writing drawing functions:

- Every function should start from the turtle's current position (instead of making the turtle move or turn
  before starting.)
- Every function should leave the turtle in the same place as it started, and pointing the same direction.
- When drawing shapes, the turtle should turn to the right.

## Notes

- Check out the {{< ref_module "lab_functions" >}} for a reminder on how functions work.
- Currently, each function does nothing. However, it's a syntax error if you don't write anything
  on the line following a function definition. That's where `pass` comes in handy: it's an instruction
  that means "do nothing" (like in a game, when it's your turn, you can pass if you don't want to do anything).
  You should replace `pass` with code that makes each function work.
- `polygon(size, num_sides)` is tricky, and requires some mathematical creativity. If you didn't figure this one
  out during the lab, look at the functions for `triangle`, `square`, `pentagon`, and `hexagon` (3, 4, 5, and 6 sides)
  and see if you can figure out how to express the pattern in a general way.
- If you get stuck on one function, it might help to create a separate file where you just define that function and
  then write some code that tests it out. (Break big problems down into smaller problems!)

## Starter code

Save this as `unit_00/YOURSTUDENTID_homework_04.py`.

```python
    # Unit 0 Lesson 4
    # Author: Your Name

    from turtle import *

    def fly(x, y):
        "Picks up the pen, goes somewhere, and then puts the pen back down."
        penup()
        goto(x, y)
        pendown()

    def square(size):
        "Draws a square with each side having a side length of `size`."
        pass

    def triangle(size):
        "Draws a triangle with each side having a side length of `size`."
        pass

    def star(size):
        "Draws a 5-pointed star. Each line has length of `size`."
        pass

    def rectangle(side1, side2):
        "Draws a rectangle."
        pass

    def grid(size, rows, columns):
        "Draws a grid of squares"
        pass

    def polygon(size, num_sides):
        "Draws the requested polygon. For example, `polygon(20, 4)` draws a square of size 20."
        pass

    # DON'T CHANGE ANYTHING BELOW HERE. THIS CODE USES YOUR FUNCTIONS... IF YOUR FUNCTION WORKS PROPERLY,
    # THIS CODE WILL DRAW THE FIGURES :)

    if __name__ == '__main__':
        fly(-100, 100)
        #Draws increasing squares
        square(20)
        square(30)
        square(40)
        fly(0, 100)
        #Draws increasing triangles
        triangle(20)
        triangle(30)
        triangle(40)
        fly(100, 100)
        #Draws increasing stars
        for i in range(1,8):
            star(5*i)
            forward(5*i)
        fly(-100, 0)
        #Draws rectangle formation
        for x in range(10, 100, 10):
            rectangle(x, 100-x)
        fly(0, 0)
        #Draws grid formation
        grid(10, 3, 4)
        fly(100, 0)
        #Draws polygon formation
        setheading(0)
        for num_sides in range(3,10):
            polygon(20, num_sides)

        input("Press enter to continue...")
```

## Deliverables

- A file called `unit_00/YOURSTUDENTID_homework_04.py`, uploaded.
- The function definitions of `square`, `triangle`, `star`, `rectangle`, `grid`, and
  `polygon` should be filled in. If they are correct, you'll see the drawing above.
- Make sure the functions follow the conventions listed above (for example, the turtle
  should always end up in the same place she started).
