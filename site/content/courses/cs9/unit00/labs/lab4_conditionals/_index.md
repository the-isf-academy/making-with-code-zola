---
title: 4. Conditionals
type: labs
# draft: true
---

# Conditionals
In this lab, we'll introduce a new concept that will
allow us to make even more interesting drawings: conditionals.

## [0] Conditional behavior

One of the most powerful ways to utilize computation is to change the behavior of our code based on context. This might sound complicated, but as a human you are very familiar with this kind of response.

There are many situations where you change your behavior based on the environment. For example, if it is raining outside, you wear rain boots. Otherwise, you might wear a different kind of shoe like tennis shoes.

You probably have even more complicated environmental responses as well.

**For example, if you are ordering bubble tea, your order might go like this:**
* If the shop has taro,
    * you get taro in your tea
* If the shop doesn't have taro but has pearl
    * you get pearl in your tea
* Finally, in the case that the shop doesn't have taro or pearl
    * you don't order any bubble tea.

In computer science, **we call this kind of behavior `conditional`**: your code runs only in the case that some condition is satisfied.

### [Conditions]
**In computer science, conditions are binary. They are either `True` or `False`, never in-between.** To create these conditions, we can use comparison operators to compare values.

{{< code-action "Guess what condition the following comparisions will evaluate to." >}}  You
can test your guesses by typing these conditions into the Python shell.

To enter a Python shell, just type `python3` into your terminal.

```python
2 < 3
```

```python
2 == 3
```

```python
"Gold" == "Silver"
```

```python
"Gold" == "Gold"
```
{{< checkpoint >}}
**Using the Python shell to experiment, fill out the chart below in your notebook.**

Python has the following comparison operators: `<`, `>`, `==`, `<=`, `>=`, `!=`.

 Be sure to define what each of the operators does and give an example of when the operator will generate a `True` condition and when the operator will generate a `False` condition:

| Operator | Description | True condition example | False condition example |
|----------|-------------|------------------------|-------------------------|
| `<`      |             |                        |                         |
| `>`      |             |                        |                         |
| `==`     |             |                        |                         |
| `<=`     |             |                        |                         |
| `>=`     |             |                        |                         |
| `!=`     |             |                        |                         |

{{< /checkpoint >}}


## [1] Conditionals
Using the conditions generated by comparison operators, you can conditionally execute pieces of your code. This is useful for changing what your code does to respond to different conditions
of the program.

### [if statements]
`if` **statements are the beginning to every conditional code block.** The code written inside the code block that follows only runs if the condition after the `if` evaluates to `True`.

```python
for i in range(20):
    if i < 10:
        print("Smaller than 10")
```

### [else statements]
`else` **statements** can be paired with `if` statements to create an alternative block of code to **execute if the condition after the `if` evaluates to `False`.**


What is the difference between the following two programs?


```python
# [else: example 1]
for i in range(20):
    if i < 10:
        print("Smaller than 10")
    print("Greater than or equal to 10")
```

```python
# [else: example 2]
for i in range(20):
    if i < 10:
        print("Smaller than 10")
    else:
        print("Greater than or equal to 10")
```
{{< checkpoint >}}

**In your notebook, write what each example will output.**
{{< /checkpoint >}}

### [elif statements]
Finally, `elif` **statements** ("else if") can be used to **create multiple branches of a conditional.** These statements add another condition to check if the condition above them does not pass.

The following program creates three branches of execution:

```python
for i in range(20):
    if i < 10:
        print("Smaller than 10")
    elif i < 15:
        print("Greater than 9 but less than 15")
    else:
        print("Greater than or equal to 15")
```

This conditional creates the folloing cases for the variable `i`:

1. i < 10
1. 10 <= i < 15
1. 15 <= i


## [2] Conditionals: User Input

{{< code-action "Create new folder in your cs9/unit_00 folder called" >}} `lab_04_conditionals`. **In the** `lab_04_conditionals` **folder, create a new file called** `conditionals_user_input.py`. **Copy and paste the code below into your file.**


```python
######################
# Unit 0 Lab 4
# Author: Your Name
#######################

# INTRO TO CONDITIONALS

from turtle import *
speed(10)
while True:
    drawing = input("What would you like me to draw? ")
    size = int(input("How big should I draw it? "))
    if drawing == "square":
        for i in range(4):
            forward(size)
            right(90)
    elif drawing == "quit":
        break
    else:
        print("Sorry, I don't know how to draw that...")
```

One way to use conditionals in our drawings is to use them to respond to user input.

{{< code-action "Run the program to see how it uses a conditional based on user input." >}}

This program has a lot of potential, but so far it can only generate one drawing.

{{< code-action "Add at least two more branches to the conditional so that the program can draw more shapes." >}}  An `elif` statement will probably be useful here.

{{< checkpoint >}}
Answer the following check-in questions in your notebook before moving on:

0. What is the difference between `else` and `elif` statements in a conditional?
0. What is the difference between `=` and `==`?
0. When writing a conditional, what kinds of things can you compare? Can you compare different
types of things to each other?
{{< /checkpoint >}}

## [3] Modulo

Python has many operators that allow you to perform calculations with values. You've probably
seen and used the basic ones like `+`(add), `-` (subtract), `*` (multiply), and `/` (divide).

However, Python has some other less common opertors that can be really helpful.

One such operator is **the modulo operator** (`%`). This operator **takes two values, divides them, and returns the remainder of the division.**

{{< checkpoint >}}

**Using the Python shell to experiment, fill out the chart below in your notebook.**

| Calculation | Result |
|-------------|--------|
| `5%3`       |        |
| `3%3`       |        |
| `6%2`       |        |
| `0%6`       |        |
| `5%0`       |        |

{{< /checkpoint >}}



### [Rainbow]
Conditionals can also be paired with the modulo operator to cause your code to run in repeated
patterns.

{{< code-action "Create a new file called" >}} `conditionals_modulo.py` **and copy and paste the code below.**

```python {linenos=table}
######################
# Unit 0 Lab 4
# Author: Your Name
#######################

# MODULO: RAINBOW

from turtle import *
speed(10)
for i in range(5):
    color("red")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("orange")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("yellow")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("green")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("blue")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("purple")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()
    color("violet")
    begin_fill()
    for j in range(4):
        forward(100)
        right(90)
    end_fill()
    penup()
    right(45)
    forward(10)
    left(45)
    pendown()

input()


```

This code is really long. However, there is a pattern to the rainbow that we could use
to simplify the code: the rainbow has 7 colors that repeat every time the loop runs for 5
iterations.

{{< code-action "Simplify this code using a conditional and the modulo operator." >}} Your file should be less than 40 lines of code.

## [3] Deliverables

{{< deliverables "Please submit your lab by copying your files into your CS9 Google Drive folder and answering the prompt in your notebook." >}}

**Files:**
- `conditionals_user_input.py`
- `conditionals_modulo.py`

Answer the following prompts in your notebook before moving on:

0. How would you describe the modulo operator to a friend who has never heard of it before?
0. Describe a moment when your code didn't do what you intended. How did you fix it?

{{< /deliverables >}}

## [4] Extension