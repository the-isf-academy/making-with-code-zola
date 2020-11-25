---
title: 0. Lists
type: labs
---

# Lists
In this mini lab, we will learn about lists, a useful data structure. 

## A. What is a list?

We call lists a **data structure** because they give structure to data. They put things in an ordered grouping, so you can access each element at an index. 


{{< code-action >}} Start by cloning your `lab-lists` repositor in your `cs9` folder. 
```shell
cd cs9/unit_00
git clone https://github.com/the-isf-academy/lab-lists-YOUR-GITHUB-USERNAME.git
```


{{< code-action >}} To start, open the file `list-exercises.py` and change the value of the variables `my_name` and `friend_name` to anything you want. Something like:

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


## C. LOOPING THROUGH PART OF A LIST
To give you more options, you can specify a range for your for-loop.

```python
print("But then they realized they ran out of money, so they can only buy 4 desserts. They decide to buy...")
for i in range(1, 6):
    print(cs1_dessert_list[i])
```

**Oops! This code has an error!**

The first four desserts in the cs1_dessert_list list are ice cream, brownies, mochi, and timtams.
But our code prints out mango sago, pumpking pie, tiramisu, and cheesecake. 

{{< code-action >}} Change the code to print out the first 4 desserts only.



## C. Transforming Lists 

Now, we will utilize a functional programming approach to transform lists. You will code the following functions in the `list_transformations.py` file:

{{< code-action >}} `reverse_list()` takes a list of numbers as an arguement and returns a list with the elements in reverse.

{{< code-action >}} `sort_list()` takes a list of strings or numbers as an arguement and returns a list with each element in alphabetical or ascending order. 

{{< code-action >}} `square_list()` takes a list of numbers as an arguement and returns a list with each element squared. 

{{< code-action >}} `capitalize_list()` takes a list of strings as an arguement and returns a list with the first letter of element capitalized. 


You can test your functions by running `list_transformations_view.py`: 

```shell
python3 list_transformations_view.py 
```

Correctly written functions will output: 

```shell
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

Below are a few helpful functions to transform the elements in the lists. 

| Function  | Data Type  | Explanation  |  Example |
|:-:|:-:|:-:|:-:|
| append(element)  | lists  | adds an element to the end of a list  |  my_list.append("lemonade") |
| capitalize()  | strings  | capitalizes the first letter in a string | my_string.capitalize()  |
| sort()  | strings, numbers  | organizes elements in a list | my_list.sort()  |



## D. Deliverables
For this lab, you should push your respository with the following:

- list-exercises.py
- list_transformations.py
- list_transformations_view.py 
- Your Google Doc with responses to the checkpoint questions

