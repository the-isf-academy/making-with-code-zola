---
title: 5. While Loops
type: labs
# draft: true
---

## [2] While loops

In addition to `for` loops which run for a set number of iterations, Python has another type
of loop. `while` loops iterate until a particular condition is met.

{{< tabs id="While-loops" >}}

{{< tab "Text Explanation" >}}
### Conditions
`while` loops use conditions just like `if` statements. You can use operators to compare
values in or to generate `True` or `False` conditions. Looping until a condition is met
can be useful when you are getting getting input from a user, generating random variables,
or repeatedly applying a transformation to a value.

```python
user_input = -1
while user_input < 1 and user_input > 10:
    user_input = input("Tell me a number between 1-10 (inclusive): ")
```

### While True / Break
You can also make `while` loops run indefinitetly by setting the condition to `True` like
this: `while True:`. This can be useful when you want to loops a program repeatedly.

To stop a loop like this, you can use a `break` statement. Once the program reaches the
`break`, the loop will exit.

You've actually already seen an example of this kind of loop at the beginning of the lab.

```python
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
{{< /tab >}}

{{< tab "Video Explanation" >}}

{{< youtube "D0Nb2Fs3Q8c" >}}
{{< /tab >}}

{{< /tabs >}}



### [Hailstone sequence]
In the last part of this lab, you will be exploring a special sequence known as the
hailstone sequence. This sequence results from the following rules (known as the Collatz
conjecture):

- take any positive number `n`
- find the next term of the sequence using the following rules:
    - if `n` is even, the next term is `n/2`
    - if `n` is odd, the next term is `n*3+1`
- repeat until `n = 1`

The conjecture states that no matter the starting value of `n`, the sequences will always
reach 1.

{{< write-action >}} Try this out: pick a number and perform the calculations. Can you find a
number that doesn't reach one?

This sequence is interesting because though no number has ever been found that doesn't reach 1,
the Collatz conjecture has never been proven. **This is an unsolved problem in mathematics!**

### C.0 Calculating hailstone sequences

#### Pseudo-code
This is another alogrithm which will require pseudo-code to figure out.
{{< write-action >}} Write out pseudo-code to plan the logic of this program.

Here are some things to consider:
- This program will require a loop. What kind of loop do you think is best? Remember that
for loops run for a definite number of times and while loops run until a condition is met.
- You will need to determine if each term is odd or even. What are some characteristics
of even numbers that will help you determine if a number is even?
- In addition to calculating each term, you should also count how many steps it takes to
reach zero and report this number at the end. You should use a `count` variable
to track the number of steps.

#### Code
Once you've completed your pseudo-code, you can translate it into Python code.

{{< code-action >}} Use the following to get started:

```python
# HAILSTONE
num = int(input("What number should I calculate the hailstone sequence of? "))

# Put your code here

print("Took " + str(count) + " steps to reach 1.")
```

{{< checkpoint >}}
Answer the following check-in questions on your group's Google doc before moving on:

0. What kind of loop did you choose to write the hailstone sequence algorithm? Why did you choose
this kind of loop?
0. Why do you think the Collatz conjecture is so hard to prove for all positive integers?
{{< /checkpoint >}}

### C.1 Drawing Hailstone
The sequences formed are known as hailstone sequences, because the terms move up
and down but ultimately reach 0 like hailstones gaining layers of ice in a cloud.

{{< figure src="images/courses/cs9/unit00/00_conditionals_hailstone_cloud.png" width="100%" title="Hailstones froming in a cloud" >}}

This pattern can lead to some interesting visualizations of hailstone sequences.

You can visualize the terms in a sequence starting with a specific number:
{{< figure src="images/courses/cs9/unit00/00_conditionals_hailstone_terms.png" width="100%" title="Terms in hailstone sequence starting at 590" >}}

Or you can visualize the number of steps it takes to reach one from a set of integers:
{{< figure src="images/courses/cs9/unit00/00_conditionals_hailstone_steps.png" width="100%" title="Steps to reach one in hailstone sequence as radii of half circles for integers 1-100" >}}

{{< code-action >}} Use your hailstone sequence code from part C.0 to create a visualization fo the
hailstone sequence using Turtle.

## Deliverables
For this lab, you should submit the following:
- The your `lab_03.py` file with the code you wrote for each of the parts
- Your Google Doc with responses to the checkpoint questions
