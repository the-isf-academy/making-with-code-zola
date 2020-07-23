---
title: Decomposition Lab
resources:
- name: mannequin
  src: images/courses/cs9/unit00/00_decomposition_mannequin.png

---

# Decomposition Lab

{{< devnote >}}
Replace the ISF Academy repo links
{{< /devnote >}}

In this lab, we'll explore how to plan backwards from a goal, breaking a complicated problem down into simpler steps. This lab will be different from previous labs in that you will not be programming. Instead, you will study a complete project and think about how it works. But first, a brief aside about dictonaries.

## Aside: Dictionaries

Before we get into today's work, we need to learn about another data structure. Paste the starter code below into a new python file, `lab_05.py`.

```python {linenos=table}
    # lab_05.py

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

### Part A: High 🗝 Useful Data Structure

You already know about lists ({{< ref_module "lab_loops" >}}), which are a great way to store things that naturally come one after another, like subway stops on a subway line, or homework assignments in a class. We call lists a **data structure** because they give structure to data. They put things in line, so you can access each element at an index. After reading the function `my_zodiac_year` (lines 23-26), open a Python shell and import `my_zodiac_year` from the `lab_05.py` file. Run the `my_zodiac_year` function passing in your birth year as the argument:

```shell
    >>> from lab_05 import my_zodiac_year
    >>> my_zodiac_year(1995)
    I was born in the year of the pig.
```

This kind of structure works well for things that have a natural order (like zodiac cycles), but what about things that don't have a natural order to them?

A dictionary is another kind of data structure that is useful for information that does not have a natural order, like images of animals. Dictionaries connect keys to values. For each unique key (for example, an animal name like `'pig'`), a dictionary stores a unique value (like a translation `猪`). To access the values of a dictionary like the `animal_dict`, use the following syntax: `animal_dict[KEY]`.

**`quit()` the python shell**

Below the `print` statement in `PART A` in the `lab_05.py` file, print the Chinese translation of the English sentence "I was born in the year of the ..."
Access the character for your `birth_year_animal` by accessing the value in the `animal_dict`.

Open a new python shell and import and run the `my_zodiac_year` function again with your new code. Now you should see something like:

```shell
    >>> from lab_05 import my_zodiac_year
    >>> my_zodiac_year(1995)
    I was born in the year of the pig.
    我出生在猪年
```

### Part B: Dictionaries in action

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

Open a python shell and import the `describe_character` and `create_character_traits` functions from the `lab_05.py` file. Create a `character_traits` dictionary using the `create_character_traits` function and run the `describe_character` function:

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

**Stop! Once your whole group has carefully read the code in this section and can explain dictionaries, raise your hand to check in with a teacher. Your teacher is going to ask you about details in the code samples above. Make sure your group has read through them carefully.**

{{< figure src="images/courses/cs9/unit00/00_decomposition_mannequin.png" width="400px" title="Mannequin" >}}

## Getting started with decomposition
Navigate to your `unit_00` directory and download the project using `git`.

```shell
    TEA-JWOLF:unit_00 jwolf$ git clone https://github.com/the-isf-academy/mannequin.git lab_05
    TEA-JWOLF:unit_00 jwolf$ cd lab_05
```

Now you need to figure out what this code is and what it does. Decide with your group how you are going to do this. A few ideas:

- Use `tree` to list all the files.
- Read the documentation, either on [GitHub](https://github.com/the-isf-academy/mannequin) or in the README (using `atom README.md`)
- The main file is called `main.py`. Try running it to see what happens.

## Exploring `mannequin` top-down and bottom-up
*In this section, read and follow along. If you do, the questions in the next section will be easier.*

There are two main ways of thinking about complex problems: top-down and bottom-up. Top down means thinking about
the problem as a whole, and how it could be broken up into a few smaller pieces. Then each of those smaller pieces
could be broken into even smaller pieces. Bottom-up means starting with tiny chunks that are so simple we can already solve them, and using them to build gradually larger pieces, until you've solved the problem. Some people like to start with top-down thinking; others prefer bottom-up. Usually we need to use both.

Let's start top-down. Open `main.py` in Atom (`atom main.py`). It's nice and short, because most of the work is done
is done elsewhere. See if you can figure out how the code in `main.py` works, and discuss these questions with
your table group:

- The function `default_settings()` returns a dict full of settings. What do you think these do? Try changing some
  settings.
- Why would the author bother making `default_settings()` a function, instead of just defining a `dict` with the
  settings in it?
- Where does `default_settings()` get used?

Now look at what gets imported in `main.py`:

```python
    from helpers import no_delay
    from body_parts import draw_body
```

First, notice that `turtle` never gets imported. The actual drawing gets done somewhere else. We've seen `no_delay`
before (in the [drawing package](https://github.com/the-isf-academy/drawing) we played with during the [modules lab]({filename}/labs/00_modules.md)), so let's skip it. The second import statement imports a function called `draw_body`, which seems to draw a body. Let's open up `body_parts.py` to see how it works.

### Body Parts
`body_parts.py` has three sections. First, there are import statements. Second, there are a whole bunch of constants (like `TORSO_WIDTH = 40`). Third, there are five functions, each responsible for drawing a different body part. Before you study this code, skim it with your group. It's particularly important to read the comments and the `docstrings` (the string following each function). Try to get a sense of what each constant means and what each function does. Your group should be doing a lot of talking--feel free to ask a teacher if your group has questions.

Try changing some of the constants and re-running `python main.py` to see what happens.

### Going deeper
Now your group has some choices. Looking at the import statements, there are some interesting new functions
imported from elsewhere. You could open those files to learn how they work.

```python
    from turtle import right, left, back, fillcolor
    from helpers import fly, restore_state_when_finished, update_position
    from shapes import rectangle, rectangle_from_center, rectangle_from_side_edge
```

You might also have noticed that this module uses `fillcolor` to fill in shapes. You could open the [turtle documentation](https://docs.python.org/3.7/library/turtle.html?highlight=turtle#turtle.fillcolor) and read about how filling works.

You could also get a little more serious about making changes to the constants in `body_parts.py` and the settings in `main.py`. Can you pose the mannequin so she is laughing? Angry? Surprised?

## Questions
*As a group, talk about these questions. Then, each student should write answers in her own words in the `questions.md` file. Each question needs a solid explanation, probably 1-3 sentences.* **You will submit the `questions.md` file at the end of the lab.**

0. Read the [`turtle` documentation on filling](https://docs.python.org/3.7/library/turtle.html?highlight=turtle#filling). To fill in a shape, you have to call `begin_fill()` before drawing the shape and `end_fill()` afterwards. All the shapes in `mannequin` are filled. Where are `begin_fill()` and `end_fill()` actually used?
1. What does `restore_state_when_finished` do?
2. What's the difference between the `settings` in `main.py` and the constants at the top of `body_parts.py`?
3. Let's imagine you wanted to move one of the constants at the top of `body_parts.py` (for example, `HEAD_COLOR`) into the settings in `main.py` instead. What steps would you have to take? (You can actually try this if you want.)
4. In `shapes.py`, there are three different functions for drawing a rectangle. Why?   
5. The same function, `draw_arm`, is used to draw the back arm and the front arm. How does this work?                  
6. Similarly, `draw_leg` is used to draw the back leg and the front leg. The code for `draw_leg`           
  and for `draw_arm` looks suspiciously similar. Can you think of a way to combine these functions? Would this         
  be a good idea? (Yes and No are both reasonable answers--explain your preference.)                                   

## Deliverables

- Each student should submit a text file with answers to the questions above.
