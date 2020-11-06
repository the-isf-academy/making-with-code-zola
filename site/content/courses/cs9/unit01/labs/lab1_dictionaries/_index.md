---
title: 1. Dictionaries
type: labs
---

# Dictionaries 

In this mini lab, we will learn about dictionaries, another data structure. Paste the starter code below into a new python file, lab_01.py.

```python
# Unit 1 Lab 1
# Author: Your Name

#PART A
zodiac_year_list = [
    'monkey','rooster', 'dog', 'pig', 'rat', 'ox',
    'tiger', 'rabbit', 'dragon', 'snake', 'horse', 'sheep'
]

animal_dict = {
    "rat": "鼠",
    "ox": "牛",
    "tiger": "虎",
    "rabbit": "兔",
    "dragon": "龙",
    "snake": "蛇",
    "horse": "马",
    "sheep": "羊",
    "monkey": "猴",
    "rooster": "鸡",
    "dog": "狗",
    "pig": "猪"
}

def my_zodiac_year(birth_year):
    zodiac_cycle_position = birth_year % 12
    birth_year_animal = zodiac_year_list[zodiac_cycle_position]
    print("I was born in the year of the {}.".format(birth_year_animal))

#PART B
def create_character_traits():
    return {
        "courage": 8,
        "beauty": 4,
        "strength": 7,
        "empathy": 5
    }

def describe_character(traits):
        if traits["strength"] > traits["courage"]:
            print("You are a coward.")
        elif traits["strength"] == traits["courage"]:
            print("You are wise, matching your strength to your courage.")
        else:
            print("You are foolhardy.")

```


### A: High 🗝 Useful Data Structure

You already know about lists, which are a great way to store things that naturally come one after another, like subway stops on a subway line, or homework assignments in a class. 

{{< code-action >}} After reading the function `my_zodiac_year` (lines 23-26)
- Open a Python shell and import `my_zodiac_year` from the `lab_05.py` file. 

- Run the `my_zodiac_year` function passing in your birth year as the argument

```shell
python3 
>>> from lab_05 import my_zodiac_year
>>> my_zodiac_year(1995)
I was born in the year of the pig.
```

The structure of a list works well for things that have a natural order (like zodiac cycles), but what about things that don't have a natural order to them?

A **dictionary** is another kind of data structure that is useful for information that does not have a natural order. Dictionaries connect keys to values. For each unique key (for example, an animal name like `'pig'`), a dictionary stores a unique value (like a translation `猪`). 

To access the values of a dictionary like the `animal_dict`, use the following syntax: `animal_dict[KEY]`.

{{< code-action >}} `quit()` the python shell

{{< code-action >}} Print the Chinese translation of the English Sentence "I was born in the year of the <insert animal>", below the `print` statement in the `my_zodiac_year` function of `PART A` in the `lab_05.py` file. 
Access the character for your `birth_year_animal` by accessing the value in the `animal_dict`.

{{< code-action >}} Open a new python shell and import and run the `my_zodiac_year` function again with your new code. Now you should see something like:

```shell
>>> from lab_05 import my_zodiac_year
>>> my_zodiac_year(1995)
I was born in the year of the pig.
我出生在猪年
```

### B: Dictionaries in action

Dictionaries can be used to show one-to-one relationships like how words in one language are connected to words in other languages, how actions are connected to consequences, or how countries are connected to languages.

Often we use dictionaries to describe properties of an object. A hero in an adventure game is defined in `PART B`:

```python
def create_character_traits():
    return {
        "courage": 8,
        "beauty": 4,
        "strength": 7,
        "empathy": 5
    }
```

{{< code-action >}} Open a python shell and import the `describe_character` and `create_character_traits` functions from the `lab_05.py` file. Create a `character_traits` dictionary using the `create_character_traits` function and run the `describe_character` function:

```shell
>>> from lab_05 import describe_character, create_character_traits
>>> character_traits = create_character_traits()
>>> describe_character(character_traits)
You are foolhardy.
```

You can loop through a `dict` in almost the same way you can loop through a list:

```shell
>>> for trait, value in character_traits.items():
...     print("You have a {} value of {}.".format(trait, value))
You have a courage value of 8.
You have a beauty value of 4.
You have a strength value of 7.
You have a empathy value of 5.
```

{{< checkpoint >}}
Answer the following check-in questions on your group's Google doc before moving on:

0. What is a dictionary?
0. Initalize a dictionary of your course schedule with blocks as the keys and classes and the values. Include at least 3 blocks. 
0. What is the difference between a list and a dictionary? 
{{< /checkpoint >}}

### C. Game Library 

Now, let's use dictionaries and lists to create a library of games. Your finished program will output something similar to this:

```shell
--Welcome to the CS9 Game Library--
We have the following genres:
- sports
- puzzle

Select a genre to view the games available: sports
---

We have the following sports games:
- Fifa
- NBA 2K
```
##### *Paste the code block below to your lab_01.py file.*

```python
#PART C

game_library =  #Initalize your game library here

def find_game():
    print("--Welcome to the CS 9 Game Library--")
    print("We have the following genres:")
    
    #YOUR CODE GOES HERE
     
find_game()
```

{{< code-action >}} Initalize the varibale `game_library` as a dictionary with genres as the keys and a list of games as the values. 

{{< code-action >}} In the function `find_game`, output the genres and ask to select a genre. 

{{< code-action >}} Output the games available in the user's selected genre. 

## D. Deliverables
For this lab, you should submit the following:

- The your lab_01.py file with the code you wrote for each of the parts
- Your Google Doc with responses to the checkpoint questions

