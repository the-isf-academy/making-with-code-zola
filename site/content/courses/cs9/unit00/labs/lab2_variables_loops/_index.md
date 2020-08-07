---
title: 2. Variables and Loops
type: labs
---

# Variables and Loops Lab

In this lab, we will learn how to make the computer do the same instruction over and over. To get started, let's
talk about how the code we've written works in your computer.

{{< include_resource "resource_code_process" >}}

{{< include_resource "resource_python_shell" >}}

{{< checkpoint >}}
Answer the following check-in questions on your group's Google doc before moving on:

0. What does Python3 (the software) do?
0. When adding, subtracting, multipling, and dividing numbers in Python, what is
the order of operations? (Use the Python shell to test!)

{{< /checkpoint >}}

{{< include_resource "resource_variables" >}}

Let's do some tests to see more about how variables work.

### A. Variable tests

Create a new file called `lab_02.py` in atom (This should be at `~/Desktop/cs9/unit_00/lab_02.py`.) You'll be turning in
this file at the end of the lab. Copy this starter code:

```python
# Unit 0 Lab 2
# Author: Your Name

from turtle import *

# A. VARIABLE TESTS
# variable test 0
name = "Your name"
print()
print("Variable test 0")
print("Hello")
print(name)

#variable test 1
print()
print("Variable test 1")

#variable test 2
print()
print("Variable test 2")
```

#### Variable test 0
{{< code-action >}} Start by replacing `"Your name"` with your name (but keep the `""`). Now you
have *declared* the `name` variable and *assigned* your name as its value. 

{{< code-action >}} Save the file and run the program like this:

```shell
~/Desktop/cs9/unit_01$ python lab_02.py
Variable test 0
Hello
FyiSi
~/Desktop/cs9/unit_01$
```

What just happened? After storing your name in the `name` variable, `print(name`) prints out whatever
is stored in the variable.

Let's do another test. {{< code-action >}} **Type** the following lines of code so that the `variable test 0`
section looks like this:
```python
# variable test 0
name = "Your name"
print()
print("Variable test 0")
print("Hello")
print(name)
name = "Friend's name"
print("Hello")
print(name)
```

{{< code-action >}} Replace `"Friend's name"` with your friend's name.

Now our program is printing the `name` variable twice but we've assigned different values to the
variable at different places in the code. What do you think will happen?

{{< code-action >}} Run the code to find out:
```shell
~/Desktop/cs9/unit_01$ python lab_02.py
Variable test 0
Hello
FyiSi
Hello
cs9
~/Desktop/cs9/unit_01$
```

Is this the output you expected? Talk with your group about what happened when you assigned the
`name` variable twice.

#### Variable test 1
{{< code-action >}} **Type** the following lines of code under the `variable test 1` section of your program.
Replace `"color"` and `"fruit"` with your favorite color and fruit:

```python
# variable test 1
print()
print("Variable test 1")
favorite_color = "color"
print("Your favorite color is " + favorite_color)
print("Your favorite fruit is " + favorite_fruit)
favorite_fruit = "fruit"
```

{{< code-action >}} Try running the program now with `python lab_02.py`

Hmm, something is wrong here. Work with your group to find and fix the bug.

#### Variable test 2
{{< code-action >}} **Type** the following lines in the `variable test 2` section of your program:
```python
# variable test 2
print()
print("Variable test 2")
favorite_artist = input("What is your favorite artist? ")
print("Oh, I love " + favorite_artist + "!")
```

{{< code-action >}} Run your program multiple times and change up what artist you type.

This shows how your programs can be responsive to user input and how you can store
information from the user in variables that may change every time your program runs.

{{< aside >}}
You can get input from the user while your program is running using `input(PROMPT)`.

If you want to get a number from the user, use `int(input("PROMPT"))`. This is because
Python treats numbers and words differently. We'll talk more about this next unit.
{{< /aside >}}
{{< checkpoint >}}
Answer the following check-in questions on your group's Google doc before moving on:

0. What is a variable?
0. How do you declare a variable?
0. What is the scope of a variable?
{{< /checkpoint >}}

## Loops

In Python, when you want to run the same code multiple times, we use loops.
If you have used Scratch before, you have seen loops before:

{{< figure src="images/courses/cs9/unit00/00_loops_scratch_loop.png" width="200px" title="Scratch loop" >}}

How does a loop work in python? Let's see.

{{< code-action >}} Copy and paste the following code into your `lab_02.py` file:

```python

```
**Do these and check with your group if you get stuck:**  

### B. Calculations
Let's start by performing some calculations for many numbers.

 {{< code-action >}} **Type** this starter code at `YOUR CODE HERE (B)`.

```python
# LOOPING THROUGH A LIST
for num in range(10):
    print(num)
```

**B.0.** {{< code-action >}} Run your program and see what gets output.

This loop runs 10 times, repeating everything indented to the right of the `for num in range(10):` line.
`num` is a variable that gets incremented by one every time the loop runs. 

**B.1.** {{< code-action >}} Edit the code to make the loop run a different number of times, maybe 5 or 14.
Can you figure out how to do it? 

Notice that the count inside `num` starts at 0 and goes up to the number inside `range()` but
doesn't include that number.

**B.2.** {{< code-action >}} Finally, edit the code to make the loop print out the square of every number
from 0 to 12. When you run your program, the output should look like this:

```shell
$ python lab_02.py
0
1
4
9
16
25
36
49
64
81
100
121
```

{{< aside >}}
If you don't want code to be executed when you run a program, you can comment it
out by placing `#` at the beginning of the line.

If you don't wan't to run the code you wrote in the first part of the lab, just
comment it out.
{{< /aside >}}

### C. Factorials
Loops are particularly useful when we need to do things over time. To see this,
let's use a loop to calculate the factorial of a number.

{{< aside >}}
The factorial of an integer (`n!`) is the product of the integer and all
the integers below it. So, `4! = 4*3*2*1 = 24`.

By definition, `0! = 1`.
{{< /aside >}}

{{< code-action >}} **Type** this code  at `YOUR CODE HERE (C)`.

```python
num = int(input("What number do you want to find the factorial of? "))

print("Factorial of " + str(num) + " is " + str(factorial))
```

**C.0.** {{< write-action >}} To get started, think through the *pseudo-code*
of what we want this program to do. *Pseudocode* is an outline of the program
we'll ultimately write where we don't worry about using Python syntax.
2. **Oops! This code has an error!**

  - The first four desserts in the `cs1_dessert_list` list are ice cream, brownies, mochi, and timtams.
  - But our code prints out brownies, mochi, timtams, creme brulee, and mango sago.
  - Change the code to print out the first 4 desserts only.

### D. Fibonacci


### G. Loopy drawings

### H. Variable drawings

### G. Computational Art

### H. Drawing Fibonacci

## Deliverables
- Once you've reached the end of the lab (or class time is over), please submit the `lab_02.py` file you have been creating
- Each member of your group should submit their own file.
- You will get credit even if you don't finish parts A-G.
