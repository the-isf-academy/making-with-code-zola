---
title: "Code Practice Homework"
type: module
---
{{< devnote >}}
Code block style: Do we want to use the black background / white text format? Also how do want to handle references to HK teaching team? (replace with generic "instructor" or "teaching team"?)
{{< /devnote >}}

# Code Practice Homework

{{< expand "Part 0: Who are you? (5 minutes)" >}}
Send your teaching team an email answering the following questions:

1. What is your name and what would you like us to call you?
2. What is one goal you have for this class?
3. What is one thing that makes you nervous about this class?
4. What is your favorite dessert?

*Note: The italicized time in brackets in each part of the homework is an estimate of the amount of time we think you should spend on each part of the homework. Don't worry if something takes you a little more or less time, but if you are spending significantly more time on some part of the homework, please reach out to your teaching team so we can figure out why :)*

{{< /expand >}}

{{< expand "Part 1: Your first program (15 minutes)" >}}
Use Python's `turtle` library to draw something. You can do this with the [functions we talked about in class](../../lessons/lesson00) or more from the [Turtle documentation](https://docs.python.org/3.7/library/turtle.html) if you want a challenge.

- Run the code to make sure it works.

    - Open a new Terminal window.
    - Navigate to the directory where your homework is saved.
    - Tell Terminal to open Atom and work on a new file

            ~$ cd Desktop/cs9/unit_00/
            ~/Desktop/cs9/unit_00$ atom homework_01.py

    - Atom should have opened.
    - Paste the starter code below into the window and save it (`⌘S`). Now you can see this file in Terminal:

            ~/Desktop/cs9/unit_00$ ls
            homework_01.py

    - Run the program.

            ~/Desktop/cs9/unit_00$ python homework_01.py


- Change the code so it draws something new. (It might help to sketch what you are trying to draw.)
- After you make a change, save the file and run the program to make sure it worked properly.
- Be ready to share your drawing in class next time we meet. **You don't need to submit anything for this part of the assignment before class.**

### Starter code

    #!python
    # Unit 0 Lesson 1
    # Author: Your Name

    from turtle import *

    # You can add comments anywhere you want. The code below draws a square.
    forward(100)
    right(90)
    forward(100)
    right(90)
    forward(100)
    right(90)
    forward(100)
    right(90)

    # This makes the program wait until you type some input.
    # Otherwise, it would quit right after it finished drawing.
    input("Press enter...")


{{< /expand >}}

# Deliverables

- An email, as described above.
- A python file called `homework_01.py`, submitted your course site.
- The program should draw something.
