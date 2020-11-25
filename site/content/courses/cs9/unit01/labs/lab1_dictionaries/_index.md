---
title: 1. Dictionaries
type: labs
---

# Dictionaries 

In this mini lab, we will learn about dictionaries, another data structure. 

{{< code-action >}} Start by cloning your `lab-dictionaries` repositor in your `cs9` folder. 
```shell
cd cs9/unit_00
git clone https://github.com/the-isf-academy/lab-dictionaries-YOUR-GITHUB-USERNAME.git
```

### A: High 🗝 Useful Data Structure

You already know about lists, which are a great way to store things that naturally come one after another, like subway stops on a subway line, or homework assignments in a class. 

{{< code-action >}} After reading the function `my_zodiac_year` in `dictionaries.py`
- Open a Python shell and import `my_zodiac_year` from the `dictionaries.py` file. 

- Run the `my_zodiac_year` function passing in your birth year as the argument

```shell
python3 
>>> from dictionaries import my_zodiac_year
>>> my_zodiac_year(1995)
I was born in the year of the pig.
```

The structure of a list works well for things that have a natural order (like zodiac cycles), but what about things that don't have a natural order to them?

A **dictionary** is another kind of data structure that is useful for information that does not have a natural order. Dictionaries connect keys to values. For each unique key (for example, an animal name like `'pig'`), a dictionary stores a unique value (like a translation `猪`). 

To access the values of a dictionary like the `animal_dict`, use the following syntax: `animal_dict[KEY]`.

{{< code-action >}} `quit()` the python shell

{{< code-action >}} Print the Chinese translation of the English Sentence "I was born in the year of the <insert animal>", below the `print` statement in the `my_zodiac_year` function of `PART A` in the `dictionaries.py` file. 
Access the character for your `birth_year_animal` by accessing the value in the `animal_dict`.

{{< code-action >}} Open a new python shell and import and run the `my_zodiac_year` function again with your new code. Now you should see something like:

```shell
>>> from dictionaries import my_zodiac_year
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

{{< code-action >}} Open a python shell and import the `describe_character` and `create_character_traits` functions from the `dictionaries.py` file. Create a `character_traits` dictionary using the `create_character_traits` function and run the `describe_character` function:

```shell
>>> from dictionaries import describe_character, create_character_traits
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


{{< code-action >}} Start by initalizing a dictionary with genres as the keys and a list of games as the values. 

{{< code-action >}} Write a function that will print the genres to the terminal and ask the user to select one. 

{{< code-action >}} Output the games available in the user's selected genre. 

## D. Deliverables
For this lab, you should push your respository with the following:

- The your dictionaries.py file with the code you wrote for each of the parts
- Your Google Doc with responses to the checkpoint questions

