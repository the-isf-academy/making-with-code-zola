---
title: 1. Lists
type: labs
---

# Lists
In this lab, we will learn about lists, a useful data structure. 

## A. What is a list?

We call lists a **data structure** because they give structure to data. They put things in an ordered grouping, so you can access each element at an index. 


{{< code-action >}} Start by cloning your `lab-lists` repositor in your `cs9` folder. 
```shell
cd cs9/unit_01
git clone https://github.com/the-isf-academy/lab-lists-YOUR-GITHUB-USERNAME.git
```


{{< code-action >}} To start, open the file `list_intro.py` and change the value of the variables `my_name` and `friend_name` to anything you want. Something like:

```python
#VARIABLES
my_name = "Wall-E"
friend_name = "Eva"
```

{{< code-action >}} The program currently prints out "help! I am trapped inside the computer!". **Replace that string with the following objects one at a time.** For each one, save your program and run it to see what the output.

0. cs1_dessert_list
0. cs1_dessert_list[0]
0. cs1_dessert_list[3]
0. cs1_dessert_list[-1]
0. len(cs1_dessert_list)
0. cs1_dessert_list[100] (Error! Why?)
0. my_name + " likes to eat " + cs1_dessert_list[0] + " but " + friend_name + " likes to eat " + cs1_dessert_list[1]


## B. Looping through a list

*Paste the code block below into the 'Part B' section of your list_intro.py file.*

```python
print("Mr. Wolf, Ms. Brown, and Mr. Chau go to the store for dessert. They decide to buy...")
for thing in cs1_dessert_list:
    print(item)
```

In the loop above, `thing` is a variable that we use to store each element within cs1_desserts as we loop through one by one. `thing` is not a very descriptive variable name - there are lots of things in the world. How will we know what thing the variable is storing?

{{< code-action >}} **Try changing `thing` to a more descriptive word in both lines**, like `sweet` or `dessert_item` and see if the output changes.


## C. Looping Through Part of a List 
To give you more options, you can specify a range for your for-loop.

*Paste the code block below into the 'Part C' section of your list_intro.py file.*


```python
print("But then they realized they ran out of money, so they can only buy 4 desserts. They decide to buy...")
for i in range(1, 6):
    print(cs1_dessert_list[i])
```

**Oops! This code has an error!**

The first four desserts in the cs1_dessert_list list are ice cream, brownies, mochi, and timtams.
But our code prints out mango sago, pumpking pie, tiramisu, and cheesecake. 

{{< code-action >}} **Change the code to print out the first 4 desserts only.**



## D. Transforming Lists 

Now, we will utilize a functional programming approach to transform lists. 

{{< figure src="images/courses/cs9/unit01/01_list_function_diagram.png" width="600px">}}


You will code the following functions in the `list_transformations.py` file:

{{< code-action >}} `reverse_list()` 
- Takes a list of any data type as an arguement 
- Returns a new list with the elements in reverse

{{< code-action >}} `square_list()` 
- Takes a list of numeric items as an arguement
- Returns a new list with each element squared

{{< code-action >}} `capitalize_list()` 
- Takes a list of strings as an arguement
- Returns a new list with the first letter of each item capitalized

{{< code-action >}} `sort_list()` 
- Takes a list of numeric items or a list of strings as an arguement
- Returns a new list with items organized numerically or alphabetically 

<br>

Here are a few helpful functions to transform the elements in the lists. 

| Function  | Data Type  | Explanation  |  Example |
|:-:|:-:|:-:|:-:|
| append(element)  | lists  | adds an element to the end of a list  |  my_list.append("lemonade") |
| capitalize()  | strings  | capitalizes the first letter in a string | my_string.capitalize()  |
| sort()  | strings, numbers  | organizes elements in a list | my_list.sort()  |

<br>

Correctly written functions will output the below when `list_transformations_test.py` is ran.

```shell 
> python list_transformations_test.py

--Number List Transformations---
Initial Number List: [25, 10, 20, 15, 5]
Numbers revered: [5, 15, 20, 10, 25]
Numbers sorted: [5, 10, 15, 20, 25]
Numbers squared: [25, 100, 225, 400, 625] 

--Word List Transformations---
Inital Word list: ['hello', 'banana', 'office', 'pie']
Words reversed: ['pie', 'office', 'banana', 'hello']
Words sorted: ['banana', 'hello', 'office', 'pie']
Words capitalized: ['Banana', 'Hello', 'Office', 'Pie']
```

<br>




{{< checkpoint >}}
Answer the following exit questions on your Google doc before submitting this lab:

0. What is a list and why is it useful? 
0. What are the benefits of using a functional programming approach to list transformations?
0. How could you have utilized lists in your Unit 0 project?


{{< /checkpoint >}}

## E. Deliverables
For this lab, you should submit the following...

- `lab-lists` repository containing the following: 
    - list_intro.py
    - list_transformations.py
    - list_transformations_view.py 
- Your Google Doc with responses to the checkpoint questions

## F. Extension
In section D, you utilized the `sort()` function to organize elements of a list. Python takes care of the logic behind the sorting for you. All you have to do is tell Python which list to sort. 

The extention activity is is for you to think through the logic of the sorting algothirm. In your Google Doc, write pseudocode for the `sort()` function. 

Some questions to consider:
- What are the steps involved in sorting a list of items? 
- What if the list contains numbers? What if the list contains strings? 
- What if the list contains numbers and strings? 

