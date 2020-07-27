---
title: Modules Practice Homework
type: checkup
---
# Practice Using Modules

Today's homework is open-ended. Keep working on the drawing you started in the {{< ref_module "lab_modules" >}}, or start a new one. Either way, see what you can make, and be ready to share it in class. Your homework should use at least one function from the `drawing` package.

We are going to add one extra step. Remember how when you imported `homework_01`, it instantly drew a picture? This is not always what we want. Sometimes, we want to import code from a module without running it right now. You can put the code inside a function. Even better, there's a trick we can use that will run the function when you run this module directly (with `python homework_05.py`, but not when you import it from another python program. We have used this trick before, in {{< ref_module "hw_functions_practice" >}}. (Don't worry about how it works for now!)

Also, in this homework, you're not allowed to import `*` from turtle. Instead, just import what you need.

## Starter code

```python
    from drawing.lines import rainbow
    from turtle import forward, right, circle

    def draw_picture():
        "Draws a picture of a rainbow whale."
        # YOUR CODE HERE
        pass

    if __name__ == '__main__':
        draw_picture()
```

## Deliverables

- Upload a file called `homework_05.py`.
- The file should contain a function that draws a picture.
- Use the `if __name__ == '__main__':` trick shown in the starter code to run the picture-drawing function
- Use at least one function from the `drawing` package.
- Don't import `*` from turtle.
