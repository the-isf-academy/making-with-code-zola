---
title: 2. Variables
type: lab
slug: lab2_variables
repo_url: https://github.com/the-isf-academy/lab-terminal-adventure
init_action: clone
# draft: true

---

# Variables Lab
In this lab, we will learn about variables, a powerful storage container of information.

## [0] Variable tests

{{< code-action "mwc update" >}} 

{{< code-action "Go to right location" >}} 

{{< code-action "look at files" >}} 



### [Variable test 0]

{{< code-action "Open the first file" >}} 
```python
#####################
# Unit 0 Lab 2 
# variable_tests0.py
#####################

name = "YOUR NAME"
print("Hello")
print(name)
```

{{< code-action >}} Start by replacing `"Your name"` with your name (but keep the `""`). Now you have *declared* the `name` variable and *assigned* your name as its value.

{{< code-action "Save the file and run the program again." >}} You should see an output similar to the one below:
> *Tip: Use the up arrow to cycle through your previous commands in Terminal*

```shell
~/Desktop/cs9/unit_01$ python lab_02.py
Hello
Emma
```

What just happened? After storing your name in the `name` variable, `print(name)` prints out whatever is stored in the variable.

Let's do another test. 

{{< code-action "Add the following lines of code to your file." >}} 

```python
name = "YOUR FRIEND'S NAME"
print("HELLO")
print(name)
```

{{< code-action >}} **Replace** `"Friend's name"` **with your friend's name.**

Now our program is printing the `name` variable twice but we've assigned different values to the
variable at different places in the code. What do you think will happen?

{{< code-action "Run the code to find out!" >}} You should see an output similar to the one below:
```shell
~/Desktop/cs9/unit_01$ python lab_02.py
Hello
Emma
Hello
Britte

```


### [Variable test 1]

{{< code-action "Copy the code block below into your file." >}} 
Replace `"color"` and `"fruit"` with your favorite color and fruit:

```python
print("-- [variable test 1] --")
favorite_color = "color"
print("Your favorite color is " + favorite_color)
print("Your favorite fruit is " + favorite_fruit)
favorite_fruit = "fruit"
```

{{< code-action "Run the program again" >}} 

Hmm, something is wrong here. Work with your group to find and fix the bug.

{{< checkpoint >}}
In your notebook, describe the bug and how you fixed it. 

Before moving on, check in with a teacher. 
{{< /checkpoint >}}

### [Variable test 2]
{{< code-action "Copy the code block below into your file"  >}}
```python
print("-- [variable test 2] --")
favorite_artist = input("What is your favorite artist? ")
print("Oh, I love " + favorite_artist + "!")
```

{{< code-action "Run your program multiple times and change up what artist you type." >}} 

This shows how your programs can be responsive to user input and how you can store
information from the user in variables that may change every time your program runs.


{{< checkpoint >}}
Answer the following check-in questions in your notebook before moving on. 

0. What is a variable?
0. How do you declare a variable?
0. At what point in a program can you use a variable?
{{< /checkpoint >}}

## [1] Responsive Drawing



The last variable test showed how your programs can be responsive to user input and how you can store information from the user in variables that may change every time your program runs.

This means that we can use variables to make our code do different things at different times based on input. Can you imagine how that might help use make more interesting turtle drawing?

{{< code-action "In a new file, create a turtle drawing that is responsive to user input." >}} Create your drawing in a file called `lab_02_drawing.py`. 


{{< aside "FYI" >}}
You can get input from the user while your program is running using `input("PROMPT")`.

If you want to get a number from the user, use `int(input("PROMPT"))`. This is because
Python treats numbers and words differently. We'll talk more about this next unit.
{{< /aside >}}


### [Deliverables]

{{< deliverables "Please submit your lab by copying your files into your CS9 Google Drive folder. and answer the following in your notebook:" >}}
- Describe a moment where your code didn't do as intended. How did you debug it? 
{{< /deliverables >}}

## [2] Extension: Size Factor Drawing

{{< code-action "In a new file, create a turtle drawing of a face that changes sizes based on a user inputed size factor." >}} Create your drawing in a file called `lab_02_extension.py`. 

For example, if the user inputs `1` the face should be an average size. If the user inputs `.5`, the face should be half size. If the user inputs `2`, the face should be twice the size. 
