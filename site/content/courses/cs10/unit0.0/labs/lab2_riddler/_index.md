---
title: "2. Riddler"
type: lab
slug: lab-riddler
repo_url: https://github.com/the-isf-academy/lab-riddler
init_action: clone
# draft: true
---

# Riddler

In this lab we will remind ourserlves of classes and object-oriented programming with a riddle guessing game. It's up to you to use the `Riddle` class to create working game. 

{{< figure src="https://play-lh.googleusercontent.com/DqluLBHRQ1VwCz13_2vIwSq3dEknwGjqXi3CXu10YC_Le-KRldpIZUtMOHgRPchui7A" width="25%"  >}}



## [0] Setup

{{< code-action "Start by opening the Terminal cloning this lab onto your laptop." >}} As a reminder, we will run this command at the start of each lab.
```shell
mwc update
```

{{< code-action "In the Terminal, type the following command to open the lab folder." >}}
```shell
cd ~/desktop/making_with_code/cs9/unit0.0_review/lab-riddler
```

{{< code-action "Enter the Poetry Shell." >}} We will run this command at the start of each lab, but only when we are inside a lab folder.
```shell
poetry shell
```
{{< aside "Exiting the poetry shell" >}}
When you want to exit the shell, you can type `exit` or `^D`
{{< /aside >}}

This repository has two files:
- `riddle.py`: This file had the `Riddle` class and a list of `Riddle` objects
- `game.py`: When run, this file should play the riddle guessing ame

---

## [1] Riddle Object

Let's start by exploring the `Riddle` object. It has two properties and one method. 
```python
class Riddle:
    def __init__(self,prompt,answer):
        self.prompt = prompt
        self.answer = answer


    def check_guess(self,guess):
        """Checks whether a guess is correct.
        Uses the fuzzywuzzy library to accept guesses which are close to the answer.
        """
        min_fuzz_ratio = 80
        similarity = fuzz.ratio(guess.lower(), self.answer.lower())
        
        if similarity >= min_fuzz_ratio:
            return True
        else:
            return False
```
> *To learn more about how `check_guess()` accepts guesses that are very close to the answer, you can visit the [fuzzywuzzy documentation](https://pypi.org/project/fuzzywuzzy/)*

{{< code-action >}} **Open `riddle.py` inside the interactive Python shell.** As a reminder, the Python shell is a great way to run small tests. 
```shell
python -i riddle.py
```

{{< code-action >}} **Create an instance of a `Riddle`.** 
```shell
r = Riddle('What gets wet when drying?','a towel')
```

{{< code-action >}} **Print the prompt and the answer to check you correctly created a `Riddle`.** 
```shell
r.prompt
r.answer
```

{{< code-action >}} **Try to guess the riddle by using the `check_guess(guess)` method.**
```shell
r.check_guess('a towel')
```

{{< code-action >}} **Now that you understand how to create a `Riddle`, open up `riddle.py`** 

This file contains a list of `Riddle` objects called `riddles`. Currently, there are only 2 riddles. 
```python
riddles = [
    Riddle(
        'What has to be broken before you can use it?',
        'an egg'),
    Riddle(
        'What month of the year has 28 days?',
        'all of them'
    )
]
```

{{< code-action "Add at least 3 more riddles to the list." >}} [Here](https://www.rd.com/list/easy-riddles/) is a list of riddles, but feel free to write your own!

---



## [2] Creating the Game

Now that you understand how the `Riddle` is structured, it's up to you use it and create a guessing game.

```shell
-----------------------------------
---- Welcome to the Riddler ----
----------------------------------- 
```

{{< code-action "Start by openning up" >}} `game.py`

{{< code-action >}} **It is up to you to finish the code in `game.py` to create a riddle guessing game.** The game should:
- loop each `Riddle` in the `riddles` list 
- ask the user guess
- tell the user if their guess was correct or incorrect


🕹️ **Once you've completed your game logic, play test your game!** `python game.py`


--- 

## [3] Deliverables


{{< deliverables "Congrats on completing the Riddler!" >}}  

Once you've successfully completed the Riddler be sure to fill out [this Google form](https://docs.google.com/forms/d/e/1FAIpQLScjMk5bB6NCcO5r6UQlp34qoT8hLT6XTan7NTWu-ijoP6977w/viewform?usp=sf_link).

{{< /deliverables >}}

---

## [4] Extension: Additional Features

Now that we've got a basic riddle guessing game, let's improve it!

### [Simple Imporvements]

Let's start with a few simple improvements. 

{{< code-action "Keep track of the user's guesses and provide a score at the end." >}} For example once the user guessed all of the riddles, it may print:
```shell
Score: 3/5 
```

{{< code-action "Randomize the order of the riddles." >}} Use the random library to change the order the riddles are given each time the user plays the game. 
> *You may want to look at the [Random library documentation](https://docs.python.org/3/library/random.html#module-random) for a hint*

--- 

### [Add Color]

Although the Riddler is functional, it is not the most exciting looking game. Let's spice it up with colors!

{{< code-action >}} **Explore the package [colorama](https://pypi.org/project/colorama/) to add color to your game!**

> It is already installed, but you will need to add the import statements to the top of `game.py`.

### [Difficulty Setting]

Currently, there are no difficulty settings for the game. Some riddles are easy, some riddles are difficult, and some riddles are in-between. 

{{< code-action "Implement a difficulty setting in your game to make it more accesisble." >}} Your game should allow the user between easy, medium, or hard riddles. This may require you to change the `Riddle` object and the game play flow in `game.py`.