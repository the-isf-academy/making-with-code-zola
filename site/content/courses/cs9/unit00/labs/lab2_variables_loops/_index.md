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

## Variable tests

Create a new file called `lab_02.py` in atom (This should be at `~/Desktop/cs9/unit_00/lab_02.py`.) You'll be turning in
this file at the end of the lab. Copy this starter code:

```python
# Unit 0 Lab 2
# Author: Your Name

from turtle import *

# VARIABLE TESTS
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

Let's do another test. {{< code-action >}} Add the following lines of code so that the `variable test 0`
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
{{< code-action >}} Type the following lines of code under the `variable test 1` section of your program.
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
{{< code-action >}} Type the following lines in the `variable test 2` section of your program:
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
<!---
{{< figure src="/images/courses/cs9/unit00/scratch_repeat.png" title="Scratch loop" >}}
--->

How does a loop work in python? Let's see.
**Do these and check with your group if you get stuck:**  

### A. Looping through an entire list
1. Let's print the desserts one by one.
  **Type** this starter code at `YOUR CODE HERE (A)`. Don't copy paste so you can practice typing the code! Also note the indents.

```python
# LOOPING THROUGH A LIST
print("Mr. Wolf, Ms. Han, and Mr. Ng go to the store for dessert. They decide to buy...")
for thing in cs1_dessert_list:
    print(thing)
```

2. In this loop, `thing` is a variable that we use to store each element within `cs1_desserts` as we loop through one by one.

  - `thing` is not a very descriptive variable name - there are lots of things in the world. How will we know what thing the variable is storing?
  - Try changing `thing` to a more descriptive word in both lines, like `sweet` or `dessert_item` and see if the output changes.

3. Alright! Now you try. There's a list called stars. Print every element in `star_list` using a for-loop.

### B. Looping through part of a list
To give you more options, you can specify a range for your for-loop.

1. **Type** this code  at `YOUR CODE HERE (B)` (don't copy paste, so you can practice typing).

```python
# LOOPING THROUGH PART OF A LIST
print("But then they realized they ran out of money, so they can only buy 4 desserts. They decide to buy...")
for i in range(1, 6):
    print(cs1_dessert_list[i])
```

2. **Oops! This code has an error!**

  - The first four desserts in the `cs1_dessert_list` list are ice cream, brownies, mochi, and timtams.
  - But our code prints out brownies, mochi, timtams, creme brulee, and mango sago.
  - Change the code to print out the first 4 desserts only.

### C,D,E. Looping with steps
Copy-paste this code into the file, replacing the line that says, `YOU WILL PASTE C, D, E HERE`.

```python
print(my_name + " stepped on the MTR after school, exhausted, and quickly fell asleep at a seat. Usually, the train stops at:")

# YOUR CODE HERE (C)

print("But on this particular afternoon, " + friend_name + " had hacked into the train system. The MTR was going twice as fast, and stopping at:")

# YOUR CODE HERE (D)

print("DING DONG!")
print("PLEASE STAND BACK FROM THE TRAIN DOORS.")
print("All of a sudden, " + my_name + " realized they had missed their stop! They leapt out of the train and got on in the other direction.")

# YOUR CODE HERE (E)
```

1. In part **C**, write a for loop to print all the stops starting with Kennedy Town and ending with Wan Chai, using `range`.
2. Sometimes you need even more options. Maybe you want to print every other element. That's where the `step` feature comes in. Your code for part **C** should look something like:

```python
for i in range(NUMBER1, NUMBER2):
    print(SOMETHING)
```

In part **D**, use the same code as **C**, but add another argument to range:

```python
for i in range(NUMBER1, NUMBER2, 2):
    print(SOMETHING)
```

`range()` can work with two arguments (`start`, `stop`) or with three (`start`, `stop`, `step`). If you only give two arguments, `step` is automatically set to one, and the for loop moves through the range one step at a time.
By setting the `step` to `2`, we tell the `range()` function to take two steps at a time.

3. You can also use the `step` and `range()` together to go through a list in the backwards direction. Just change the step argument to `-1`. Now, the `range()` function will walk through the range negative one step at a time. In part **E**, write a for loop to print all the stops starting with Wan Chai and ending with Sheung Wan.

    *Hint: you will also need to update the start/end argument of the `range()` function to account for the negative one step.*

### F. Looping for a certain number of times
Sometimes you don't care about the list value. You just want something to happen a certain number of times. Here's an example using range. **Type** this code (don't copy paste, so you can practice typing) into part **F**

```python
# LOOPING FOR A CERTAIN NUMBER OF TIMES
for i in range(0, 5):
    print("hello")
```

Can you print this pattern using loops? There are multiple ways to do this, with or without lists. Add this to part **F**.

```python
* * * * *
* * * * *
* * * * *
* * * * *
* * * * *
```

### G. Loopy drawings
The loop concept we just learned will be really helpful in making our drawings more complex. In part **G**, try to create the following image using tools from the Turtle library that we've covered so far.

{{< figure src="images/courses/cs9/unit00/00_loops_turtle_loop.png" width="400px" title="Turtle loop" >}}


### H. Variable drawings
Variables will also be useful in our Turtle drawings. Can you add a variable to the code you wrote for the drawing above to create the drawing below?

{{< figure src="images/courses/cs9/unit00/00_loops_turtle_var.png" width="400px" title="Turtle var" >}}


## Deliverables
- Once you've reached the end of the lab (or class time is over), please submit the `lab_02.py` file you have been creating
- Each member of your group should submit their own file.
- You will get credit even if you don't finish parts A-G.
