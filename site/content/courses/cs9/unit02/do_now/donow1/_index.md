---
title: "1. Guessing Game"
type: checkup
---
# Guessing Game

In this Do Now, you must finish the code for a number guessing game.

---

## Set up

{{< code-action "First, navigate to your cs9/donows/unit_01 folder" >}} `unit_01` **folder.**

```shell
cd Desktop/cs9
cd cs9-donows-YOUR-GITHUB-USERNAME
cd unit_02
```

{{< code-action "Create a new document" >}}
```shell
atom donow1.py
```

{{< code-action "Paste in this starter code." >}}

```python
#############
# unit02
# donow1.py
#############

from random import randint

print("-"*40)
print("--- WELCOME TO THE ISF GUESSING GAME ---")
print("-"*40, "\n")

game_won = False
random_number = randint(0,10)

guess_number = int(input("Guess a number between 0-10: "))

if guess_number == random_number:
    game_won = True

elif guess_number > random_number:
    print("  Too high... \n")

elif guess_number < random_number:
    print("  Too low... \n")

print("\n ---- You won! ----")
print("---- The number is {} ----".format(random_number))

```

## Finish the game

{{< code-action "Start by running the file, " >}} `python3 donow1.py`.

 There's no bugs, but currently the game only allows one guess. It also tells the user 'You won!', even if they guessed incorrectly. 
 

 {{< code-action "It's up to you to finish the code so the user can guess until they find the correct number." >}} 

{{< expand "Hint" >}}

*Hint: You only need to add 1 line of code*

{{< /expand >}}

When completed, the game should run like so: 
```shell
----------------------------------------
--- WELCOME TO THE ISF GUESSING GAME ---
---------------------------------------- 

Guess a number between 0-10: 5
  Too low... 

Guess a number between 0-10: 8
  Too high... 

Guess a number between 0-10: 6

 ---- You won! ----
```

{{< deliverables "Be sure to push this Do Now to Github:" >}}

- `git status`
- `git add donow1.py`
- `git commit`
- `git push`

{{< /deliverables >}}

---


### [Extension: Number of Guesses]

A common feature of guessing games is to track the number of guesses it takes the user to correctly guess the answer. It is up to you to implement this feature in this number guessing game. 

For example, the name will now run like so:
```shell
----------------------------------------
--- WELCOME TO THE ISF GUESSING GAME ---
---------------------------------------- 

Guess a number between 0-10: 5
  Too low... 

Guess a number between 0-10: 8
  Too high... 

Guess a number between 0-10: 6

 ---- You won! ----
 It took you 3 guesses to find the correct number.
```

 {{< code-action "Keep track and print the number of guesses it takes the user to find the correct answer." >}} 



