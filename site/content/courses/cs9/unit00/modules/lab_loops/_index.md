---
title: Loops Lab
resources:
- name: Scratch loop
  src: images/courses/cs9/unit00/00_loops_scratch_loop.png
- name: Turtle loop
  src: images/courses/cs9/unit00/00_loops_turtle_loop.png
- name: Turtle var
  src: images/courses/cs9/unit00/00_loops_turtle_var.png
---

# Loops Lab

In this lab, we will learn how to make the computer do the same instruction over and over.

## The Python shell

Usually, we write Python code in a file using Atom and then run it using Terminal. There's another way to run Python, which is really nice for when you just want to mess around or do a quick test. Open Terminal, navigate to your computer science directory and type `python`.

```shell
~$ cd Desktop/cs9
~/Desktop/cs9$ python
Python 3.7.3 (default, Mar 27 2019, 09:23:15)
[Clang 10.0.1 (clang-1001.0.46.3)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

See how the prompt changed to `>>>`? That tells you you're in Python world. You can type Python code here and it will run. Let's try it out. Type the following, and make sure you get the same response.

```shell
>>> 1+1
2
>>> 123456 + 654321
777777
>>> number = 5
>>> number * number
25
>>> "I am " + "a robot"
'I am a robot'
>>> exit()
~/Desktop/cs9$
```

Once you exit the Python shell, all your work is lost. So it's not a good way to do serious work, but it works great as a fancy calculator.

```shell
>>> 1+1
2
>>> 123456 + 654321
777777
```

{{< checkpoint />}}

## Variables

You are probably familiar with variables in math. ("Solve for x: `2x + 4 = 3x`") In math problems, the goal is often to figure out the secret value of a variable. Once you figure it out, the problem is finished. Variables work differently in computer science:

- You can create them whenever you want. In fact, you already made one. Remember typing `number = 5` above? You made a variable called "number" and set its value to 5.
- In computer science, you get to decide what value variables have, and you can change them whenever you want. Try this:

```shell
>>> name = "Elton"
>>> "my name is " + name
```

- You can call them whatever you want (no spaces though!) In math, variables have names like `x`, `y`, and `t`. In computer science, we usually call them things like `number_of_coins_in_my_hand` or `direction_my_character_is_facing` because it's less confusing.

We're going to learn a lot about variables this year, but that's enough for now.

---

## Lists

Create a new file called `lab_02.py` in atom (This should be at `~/Desktop/cs9/unit_00/lab_02.py`.) You'll be turning in this file at the end of the lab. Copy this starter code:

```python
    # Unit 0 Lab 2
    # Author: Your Name

    from turtle import *

    #VARIABLES
    my_name = ""
    friend_name = ""
    meme_list = ["creeper?","aw man"]
    cs1_dessert_list = ["ice cream", "brownies", "mochi", "timtams", "creme brulee", "mango sago", "pumpkin pie", "tiramisu", "cheesecake"]
    metro_stop_list = ["0 Kennedy Town", "1. HKU", "2.. Sai Ying Pun", "3... Sheung Wan", "4.... Central", "5..... Admiralty", "6...... Wan Chai"]
    star_list = ["*", "**", "***", "****", "*****"]

    # LIST EXPERIMENTS
    print("help! I am trapped inside the computer!")

    # LOOPING THROUGH A LIST
    # YOUR CODE HERE (A)

    # LOOPING THROUGH PART OF A LIST
    # YOUR CODE HERE (B)

    # LOOPING WITH STEPS
    # YOU WILL PASTE C, D, E HERE

    # LOOPING FOR A CERTAIN NUMBER OF TIMES
    # YOUR CODE HERE (F)

    # LOOPY DRAWINGS
    # YOUR CODE HERE (G)

    # VARIABLE DRAWINGS
    # YOUR CODE HERE (H)
```

We've created a ton of variables here, except this time they're in a file so we won't lose them after we run the program. Try running the program.

```shell
    ~/Desktop/cs9/unit_01$ python lab_02.py
    help! I am trapped inside the computer!
    ~/Desktop/cs9/unit_01$
```

### What is a list?
When you want to know what something is (inside a computer program), ask the program to print it out. Before we start, change the value of the variables `my_name` and `friend_name` to anything you want. Something like

```python
#VARIABLES
my_name = "Wall-E"
friend_name = "Eva"
```

The program currently prints out `"help! I am trapped inside the computer!"`. Replace that string with the following objects one at a time. For each one, save your program and run it to see what the object is.

0.  `"hello"`
1.  `goodbye` (This will cause an error. See if you can understand the error message.)
1.  `my_name`
1.  `"hello, " + my_name`
1.  `meme_list`
1.  `cs1_dessert_list`
1.  `cs1_dessert_list[0]`
1.  `cs1_dessert_list[1]`
1.  `cs1_dessert_list[2]`
1.  `cs1_dessert_list[100]` (Another error. Why?)
1.  `my_name + " likes to eat " + cs1_dessert_list[0] + " but " + friend_name + " likes to eat " + cs1_dessert_list[1]`

### What's going on?

Once you finish running all these examples, talk with your table group to explain what each one means. Here are some terms:

- A **list** is a collection of **elements** in order. When you write down a list, you use brackets on either end, and commas in between. Like this: `[100, 200, 400, 800]`.
- Each list element has an **index**. The first element's index is 0, the second's is 1, and so on. You can get a list element by using its index, like this:

```shell
>>> meme_list[0]
creeper?
>>>
```

#### CHECKPOINT: When you are confident that *everybody at your table* can explain lists, raise your hand for an instructor to check in before you go on.

---

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
