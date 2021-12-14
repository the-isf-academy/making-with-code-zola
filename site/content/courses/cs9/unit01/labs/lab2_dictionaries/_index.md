---
title: 2. Dictionaries
type: labs
draft: True

---

# Dictionaries 

In this mini lab, we will learn about dictionaries, another data structure. 


## A: High 🗝 Useful Data Structure

You already know about lists, which are a great way to store things that naturally come one after another, like subway stops on a subway line, or homework assignments in a class. 

The structure of a list works well for things that have a natural order (like zodiac cycles), but what about things that don't have a natural order to them?

A **dictionary** is another kind of data structure that is useful for information that does not have a natural order. **Dictionaries connect keys to values**. For each unique key (for example, an animal name like `'pig'`), a dictionary stores a unique value (like a translation `猪`). 

<br>


```python
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
```


<br>


{{< code-action >}} Start by cloning your `lab-dictionaries` repositor in your `cs9` folder. 
```shell
cd cs9/unit_00
git clone https://github.com/the-isf-academy/lab-dictionaries-YOUR-GITHUB-USERNAME.git
```

{{< code-action >}} Read the function `my_zodiac_year` in `dictionaries_introduction.py`
- Open a Python shell and import `my_zodiac_year` from `dictionaries_introduction.py`

- Run the `my_zodiac_year` function passing in your birth year as the argument

```shell
> python3 
>>> from dictionaries_introduction import my_zodiac_year
>>> my_zodiac_year(1995)
I was born in the year of the pig.
```

Let's add the Chinese translation the English Sentence "I was born in the year of the ________" to the `my_zodiac_year` function. 

{{< code-action >}} Below the `print` statement in the `my_zodiac_year` function of `dictionaries_introduction.py`, print the Chinese translation. Use the `animal_dict` dictionary to access the character for your `birth_year_animal`. 

**Values in a dictionary are accessed via the key.** For example:
```shell
> python3 
>>> from dictionaries_introduction import animal_dict
>>> animal_dict['dog']
'狗'
```

{{< code-action >}} Open a new python shell and import and run the `my_zodiac_year` function again with your new code. Now you should see something like:

```shell
>>> from dictionaries import my_zodiac_year
>>> my_zodiac_year(1995)
I was born in the year of the pig.
我出生在猪年
```

## B: Dictionaries in action

Dictionaries can be used to show one-to-one relationships like how capitals are connected countries, how students are connected to grade levels, or how books are connected to authors. 

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


## C. Game Library

Now, let's use dictionaries and lists to create a library of games. You will code the following functions in the `library_functions.py` file:


{{< figure src="images/courses/cs9/unit01/01_dict_function_diagram.png" width="600px">}}




{{< code-action >}} `total_num_games()`
- Paramter: a dictionary 
- Output: an integer value representing the number of games in the given dictionary 

{{< code-action >}} `get_genres()`
- Paramter: a dictionary 
- Output: a list of the genres available in a given dictionary 

{{< code-action >}} `num_games_per_genre()`
- Paramters: a genre, a dictionary 
- Output: an integer value representing the number of games available for the given genre in the given dictionary

{{< code-action >}} `get_games_for_genre()`
- Paramter: a genre, a dictionary 
- Output: a list of games available for the given genre in the given dictionary

<br>

A helpful function:

| Function  | Explanation  |  Example |
|:-:|:-:|:-:|
| keys() | returns the keys in a dictionary  |  my_dict.keys() |

<br>

To test your functions run: `python library_test.py`.

```shell
------------------------------------
--Welcome to the CS Game Library--
------------------------------------

We have 17 total games.

We have the following genres:
  - Sports
  - Puzzle
  - Multiplayer
  - RPG

Select a genre to view the games available: Sports

We have 3 Sports games:
  - Fifa
  - NBA 2K
  - Wii Sports

------------------------------------
--------Thanks for visiting!--------
------------------------------------
```

<br>

{{< checkpoint >}}
Answer the following exit questions on your Google doc before submitting this lab:

0. What is a dictionary and why is it useful? 
0. What are the similarities and differences between lists and dictionaries? 
0. Come up with 3 examples of data that could be organized using a dictionary.


{{< /checkpoint >}}

## D. Deliverables
For this lab, you should submit the following:

- `lab-dictionaries` respository
    - `dictionaries_introduction.py`
    - `library_functions.py`
    - `library_test.py`
    - `game_library.py`
- Your Google Doc with responses to the checkpoint questions

## E. Extension
As the CS game library currently stands, for each game the only available data is the title and the genre. Typically, libraries contain many more instances of metadata. For example, book metadata contains the title, author, date published, etc. 

The extension actvitiy is to create a model for a more complex game library. Each game must include the following: 
- Title
- Genre
- Publisher
- Date Released
- Platforms 

In your Google Doc, draw a model of the data strcuture. 


