---
title: 0. Lists
type: labs
---

# Lists
In this mini lab, we will learn about lists, a useful data structure. 

## A. What is a list?

We call lists a **data structure** because they give structure to data. They put things in an ordered grouping, so you can access each element at an index. 

Start by creating a `unit_01` folder in your `cs9` folder. Then paste the starter code below into a new python file, `lab_00.py`. 

```python
# Unit 1 Lab 0
# Author: Your Name

from turtle import *
import random

#PART A

##Variables
my_name = ""    
friend_name = ""

## List Experiments
cs1_dessert_list = ["ice cream", "brownies", "mochi", "timtams", "creme brulee", "mango sago", "pumpkin pie", "tiramisu", "cheesecake"]

print("help! I am trapped inside the computer!")
```

{{< code-action >}} To start, change the value of the variables `my_name` and `friend_name` to anything you want. Something like:

```python
#VARIABLES
my_name = "Wall-E"
friend_name = "Eva"
```

{{< code-action >}} The program currently prints out "help! I am trapped inside the computer!". Replace that string with the following objects one at a time. For each one, save your program and run it to see what the output.

0. cs1_dessert_list
0. cs1_dessert_list[0]
0. cs1_dessert_list[3]
0. cs1_dessert_list[-1]
0. len(cs1_dessert_list)
0. cs1_dessert_list[100] (Error! Why?)
0. my_name + " likes to eat " + cs1_dessert_list[0] + " but " + friend_name + " likes to eat " + cs1_dessert_list[1]


{{< checkpoint >}}
Answer the following check-in questions on your group's Google doc before moving on. 


0. How do you print a specific elemement in a list?
0. How do you print the length of a list? 
0. Why did cs1_dessert_list[100] result in an error? 

{{< /checkpoint >}}


## B. Looping through a list

##### *Paste the code block below to your lab_00.py file.*

```python
#PART B

print("Mr. Wolf, Ms. Brown, and Mr. Chau go to the store for dessert. They decide to buy...")
for thing in cs1_dessert_list:
    print(item)
```

In the loop above, `thing` is a variable that we use to store each element within cs1_desserts as we loop through one by one. `thing` is not a very descriptive variable name - there are lots of things in the world. How will we know what thing the variable is storing?

{{< code-action >}} Try changing `thing` to a more descriptive word in both lines, like `sweet` or `dessert_item` and see if the output changes.

*Can you think of another way to print each element of a list?*

## C. Name Generator 

Now, let's use lists to create a random name generator. Your finished program will output something similar to this:

```shell
---Medieval Generator---
Galahad Calderon
```

##### *Paste the code block below to your lab_00.py file.*

```python
#PART C

def name_generator():
    print("---Name Generator---")

    #YOUR CODE GOES HERE

name_generator()
```

{{< code-action >}} Initalize two lists, one with first names and one with last names. Feel free to come up with your own names or reference this [image](https://i.pinimg.com/564x/7e/1b/66/7e1b6694801dc8c38ce678bb49a47e6c.jpg).

{{< code-action >}} Generate a random first name and a random last name. 

You will need to utlize the Python module, **random**. Read the [Library Documentation](https://docs.python.org/3/library/random.html#module-random) to learn more. 

{{< code-action >}} Output the full name to the user


## D. Deliverables
For this lab, you should submit the following:

- The your lab_0.py file with the code you wrote for each of the parts
- Your Google Doc with responses to the checkpoint questions

