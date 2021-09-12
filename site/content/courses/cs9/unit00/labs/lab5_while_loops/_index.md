---
title: 5. While Loops
type: labs
#draft: true
---

# While loops

In addition to `for` loops which run for a set number of iterations, Python has another type of loop. `while` loops iterate until a particular condition is met.

## [0] What is a While Loop?
{{< tabs id="While-loops" >}}
{{< tab "Text Explanation" >}}
### Conditions
`while` loops use conditions just like `if` statements. You can use operators to compare
values or to generate `True` or `False` conditions. Looping until a condition is met
can be useful when you are gettin input from a user, generating random variables,
or repeatedly changing a value.

```python
user_input = -1
while user_input < 1 and user_input > 10:
    user_input = int(input("Tell me a number between 1-10 (inclusive): "))

```

### While True / Break
You can also make `while` loops run indefinitely by setting the condition to `True` like
this: `while True:`  This can be useful when you want to loop a program repeatedly.

To stop a loop like this, you can use a `break` statement. Once the program reaches the
`break`, the loop will exit.

You've actually already seen an example of this kind of loop when you learned about
conditionals in the previous lab.

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


## [1] Hailstone Sequence

### [Calculating the Sequence]
In the first part of this lab, you will be exploring a special sequence known as the
hailstone sequence.

**This sequence results from the following rules** (known as the Collatz conjecture):
- take any positive number `n`
- find the next term of the sequence using the following rules:
    - if `n` is even, the next term is `n/2`
    - if `n` is odd, the next term is `n*3+1`
- repeat until `n = 1`

The conjecture states that no matter the starting value of `n`, the sequences will always reach 1.

{{< checkpoint >}} In your notebook, pick a number and perform the calculations.

Can you find a number that doesn't reach 1?

{{< /checkpoint >}}

This sequence is interesting because though no number has ever been found that doesn't reach 1,the Collatz conjecture has never been proven. **This is an unsolved problem in mathematics!**

### [Pseudocode the Sequence]

This is another algorithm which will require pseudocode to figure out.

**Your program must:**

0. Ask the user what number the program should calculate the hailstone sequence of.
0. Print out each number in the sequence.
0. Print out how many steps it took for the sequence to reach `1`

{{< checkpoint >}}
**Write out pseudocode to plan the logic of this program.**

Here are some things to consider:
- This program will require a loop. What kind of loop do you think is best? Remember that
for loops run for a definite number of times and while loops run until a condition is met.
- You will need to determine if each term is odd or even. What are some characteristics
of even numbers that will help you determine if a number is even?
- In addition to calculating each term, you must count how many steps it takes to reach 1 and report this number at the end.
{{< /checkpoint >}}

### [Code the Sequence]

Once you've completed your pseudocode, you can translate it into Python code.

{{< code-action "Create a new folder" >}} called `lab_05_while_loops` in your `cs9\unit_00` folder.

```shell
cd cs9
cd unit_00
mkdir lab_05_while_loops
```

{{< code-action "Create a new file" >}} called `hailstone_sequence.py` in your `lab_05_while_loops` folder. Copy and paste the code below into your file.

```python
######################
# Unit 0 Lab 5
# Author: Your Name
#######################

# HAILSTONE SEQUENCE
print("--- Hailstone Sequence ---")
print()

# YOUR CODE GOES HERE

```

{{< code-action "Translate your pseudocode into Python code." >}}

{{< checkpoint >}}
Answer the following check-in questions on your notebook before moving on:

0. What kind of loop did you choose to write the hailstone sequence algorithm? Why did you choose
this kind of loop?
0. Describe a moment when your code didn't do what you intended. How did you fix it?
0. Why do you think the Collatz conjecture is so hard to prove for all positive integers?
{{< /checkpoint >}}

## [2] Deliverables
{{< deliverables "For this lab, you should submit the following:" >}}

- The your `hailstone_sequence.py` file to your CS9 Google Drive folder.
- Your notebook with responses to the checkpoint questions.

{{< /deliverables >}}


## [3] Extension: Visualizing the Sequence
The sequences formed are known as hailstone sequences, because the terms move up
and down but ultimately reach 1 like hailstones gaining layers of ice in a cloud.

{{< figure src="images/courses/cs9/unit00/00_conditionals_hailstone_cloud.png" width="100%" title="Hailstones forming in a cloud" >}}

This pattern can lead to some interesting visualizations of hailstone sequences.

{{< code-action "Use your hailstone sequence code to create a visualization for the hailstone sequence using Turtle." >}}

You can visualize the terms in a sequence starting with a specific number:
{{< figure src="images/courses/cs9/unit00/00_conditionals_hailstone_terms.png" width="100%" title="Terms in hailstone sequence starting at 590" >}}

Or you can visualize the number of steps it takes to reach one from a set of integers:
{{< figure src="images/courses/cs9/unit00/00_conditionals_hailstone_steps.png" width="100%" title="Steps to reach one in hailstone sequence as radii of half circles for integers 1-100" >}}



<br>

{{< code-action "Add a random color element to the visualization" >}}

You will need to reference the following:
- [Turtle Color Documentation](https://docs.python.org/3/library/turtle.html#turtle.color)
- [Python Random Library Documentation](https://docs.python.org/3/library/random.html)
