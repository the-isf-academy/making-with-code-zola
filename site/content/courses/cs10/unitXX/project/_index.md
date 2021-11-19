---
Title: Project
draft: false
---

# Unit Review: Terminal Game Project

In this project, you will create a game and write a terminal interface for it.


## [0] Game Options

You have four options to choose from – Spelling Bee, Yahtzee, Mastermind, or Block, Load, Shoot.

Once you get your game playable, you can then scale it up to include more complicated interactions like viewing the rules, adding random elements, improving the menus, adding more puzzles, etc.

Below are the four games that you can choose to implement. Look at the provided pseudocode and try playing each game to help you decide which you'd like to do!

### [Spelling Bee]

[To play the NTY Spelling Bee, click here](https://www.nytimes.com/puzzles/spelling-bee)

  **SpellingBee Pseudocode**

```
main game loop
    set invalid_letters to False
    user guesses a word

    iterate through each letter in the guess
        if the letter isn't one of the allowed letters
          set invalid_letters to True

    if invalid_letters is True
        tell the user not to use unallowed letters
    else if the key letter is not in the guess
        tell the user they must include the key letters
    else if the guess is already in the list of guessed words
        tell the user they have already guessed that word
    else if the guess is in the valid word list
        congratulate the user
        add the guess to the list of guessed words
    else
        tell the user that the word isn't one of the words on your list
```


### [Yahtzee]
[To play Yahtzee, click here](https://solitaired.com/yahtzee)

For this project, you will implement a simplified version of Yahtzee,
which only scores the Aces, Twos, Threes, Fours, Fives, and Sixes.
You won't have to worry about scoring the more complicated rolls,
or creating an AI opponent.

  **Yahtzee Pseudocode**
```
initialize a scoring_options list that contains the scoring options
initialize a score variable to 0
initialize a dice list to hold 5 die objects

loop 6 times
    user rolls all the dice
    display the rolled dice values
    display the scoring_options

    loop 3 times
        user chooses which dice to re-roll
        re-roll each die the user chooses

    user chooses how to score the current round
    remove the chosen scoring option from the scoring_options list
    update score variable based on this round's score

display score
```


### [Mastermind]
[To play Mastermind, click here](https://www.webgamesonline.com/mastermind/)

  **Mastermind Pseudocode**
```
set guess_limit to 10
set game_won to false

loop until the guess limit is reached or game_won is true
    set correct_pins to 0
    set right_color_pins to 0

    user guesses the pins

    if the guess is completely correct
        tell the user good job
        set game_won to true

    else
        iterate through the user's guessed pins
            if the guess pin is the same color and same position as code pin:
                increase correct_pins by 1
        overlap = set(list of guessed pins) & set(list of code pins)
        right_color_pins = (len(overlap)-right_color_pins)
        tell the user about right_color_pins and right_color_pins
```

### [Block, Load, Shoot]
You probably already know how to play this game, but incase you don't,
[here are the rules](https://ctac.esrc.unimelb.edu.au/biogs/E000331b.htm).
You can try playing with a classmate.


**Block, Load, Shoot Pseudocode**

```
set game_over to False

while game_over is False
    ask the user what they would like to do
        if the user has ammunition
            the user can choose to block, load, or shoot
        else
            the user can choose block or load

    import computer_move

    if users_choice is "Load"
        if computer_move is "Shoot"
            set game_over to True
            set user to dead
        else
            adds 1 to user's ammunition
    else if users_choice is "Block"
        display computer_move
    else if users_choice is "Shoot"
        subtracts 1 from user's ammuninition
        if opponent_move is "Load"
            game_over = True

display outcome to user
```

### [Hangman: Example Game]
We made an example Hangman game! Feel free to play and explore the code base [here](https://replit.com/@Emma-QingQing/Hangman?v=1)


## [1] Planning Document

This is a big project, and you will get lost or frustrated if you don't do some planning up front.
Before you start working on your project, you are required to write a project proposal and get it
approved by a teacher. *You can find your planning doc in your Google Drive folder called "Unit Review Terminal Games Project: Planning Document".*

## [2] Deliverables


- A `Unit Review Terminal Game Project: Design Document` in your Google Drive folder
- A `terminal-game-project` repository containing the following files:
   - `run_game.py` - when this file is run, the game should begin in the terminal. It will contain most of the logic of the game
    - `view.py` - your View class should handle all the printing to the terminal and user interactions
    - `game_object.py` - the class in this file should create the object that stores any necessary data about the game
    - `README.md` This is documentation for your project for other people who may want to use your project.
- `Unit Review Terminal Game Project: Self-Assessment` - Google doc. This is where you will self-assess your final project.


**You can find more documentation about what each of the files should contain within the README.md file.**


### [Timeline]
Click below to see a detailed timeline for your class section.

#### cs10.1
{{< expand "cs10.1 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 23 Nov 2021 | Introduction to Project |
| 25 Nov 2021 | Work Day                |
| 29 Nov 2021 | Work Day                |
| 30 Nov 2021 | Work Day                |
| 03 Dec 2021 | Work Day: Peer Review   |
| 07 Dec 2021 | Work Day                |
| 09 Dec 2021 | Work Day                |
| 13 Dec 2021 | DUE: Project & Self-assessment    |

{{< /expand >}}

#### cs9.2

{{< expand "cs10.2 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 19 Nov 2021 | Introduction to Project |
| 24 Nov 2021 | Work Day                |
| 29 Nov 2021 | Work Day                |
| 01 Dec 2021 | Work Day: Peer Review   |
| 03 Dec 2021 | Work Day                |
| 06 Dec 2021 | Work Day                |
| 08 Dec 2021 | Work Day                |
| 12 Dec 2021 | DUE: Project & Self-assessment    |
{{< /expand >}}

## [3] Starter Code
You can choose one of these four games to implement. You will create your own game class and your own view class, but you will be given pseudocode to help you with the logic of how your game driver will work.

{{< code-action >}} The three empty files that you will implement are provided in the
`terminal-game-project` repo. Download it *onto your laptop*.

```shell
$ cd cs10/unit-review
$ git clone https://github.com/the-isf-academy/terminal-game-project-CHANGE-TO-YOUR-GITHUB-USERNAME.git
```



## [3] Self-Assessment
You are responsible for assessing your own project, though your teachers will let you know if they disagree and provide a final score.

In `Unit Review Terminal Game Project: Self-Assessment`, you are required to explain how your project should be scored, and to give evidence to support your assessment. The rubric is based on claims that you should be able to make about your learning in this unit.

The self-assessment is broken down into three areas:
- Practices
    - Architecture, translating pseudocode, iterative development, and testing
- Concepts
    - Classes and backend vs frontend
- Reflection

**To do well in this project, you should be able to concretely justify that you can do each practice and understand each concept by providing evidence from your code.**

### [Practices]
Each practice is something that a computer scientist does each time they approach a problem. You are required to self-assess your ability to do each practice.

For each practice you must provide the following:
- A score from 0-3
    - 0 - little to no evidence of practice
    - 1 - below average evidence of practice
    - 2 - above average evidence of practice
    - 3 - outstanding evidence of practice
- A justification of why you deserve that score
- Examples to support your justification


### [Concepts]
This project focused on key computer science concepts, abstraction and decomposition.
You are required to demonstrate your understanding of each concept through evidence based reflection.

For each concept you must provide the following:
- A score from 0-3
    - 0 - little to no evidence or understanding of concept
    - 1 - below average evidence or understanding of concept
    - 2 - above average evidence and understanding of concept
    - 3 - outstanding evidence and understanding of concept
- A justification of why you deserve that score
- Examples to support your justification
- A discussion of why each concept is important

### [Reflection]

As we reviewed how to make and use classes, you explored how user interactions work, and the possible ways we can display information and ask for input from a user. The reflection is space for you to think more deeply about the user experience by evaluating the implications of your design choices.


*It is marked purely based on completion and demonstration of effort.*



## [4] Sucess Claims

Successful computer scientists should be able to make the following claims:
- I can thoughtfully architect a large computer science project.
  - I can use descriptive names for variables, functions, properties, methods, classes, and files
  - I can add comments that explain the purpose of each function, method, and class
  - I can document my code in the README.md
- I can turn pseudocode and flow-charts into working code
  - I use flow control, loops, functions, and methods effectively
  - I can use terminal menus where appropriate
  - I can write user interactions that make sense to the user
- I can develop my project iteratively over time
  - I can track the development of my project by committing to Github consistently throughout my project.
  - I can systematically breakdown my project into smaller chunks
- I can test my project well
  - I have tested the expected user scenarios
  - I have tested or prevented unexpected user scenarios
- I use classes effectively
  - I can create a class
  - I can import and use existing classes
  - I can write methods that use parameters and return statements
- I can separate back-end functionality from front-end functionality
  - I can keep all print statements and inputs in my view class
  - I can keep all logic in my driver file
  - I can use the game class to store the relevant data points



**Keep the success claims in mind when coding your project and self-assessing yourself.**

## [5] Scoring

The project is scored out of 7.
- 1 point is assigned to the reflection
    - *By thoughtfully answering the prompts and putting effort into your response, you will receive 1 point*
-  6 points are assigned to the practices & concepts
    - *To calculate your score for the practices & concepts, look at the following bands:*
    > 0 = 0-3
    >
    > 1 = 4- 6
    >
    > 2 = 7 - 9
    >
    > 3 = 10 - 12
    >
    > 4 = 12- 14
    >
    > 5 = 14 - 16
    >
    > 6 = 16- 18

*Example score:*

    1 point for reflection
    5 points for practices & concepts (15/18)
    6 total points

#### Final Score

Your final score for the project will take into account your self-assessed score and the teacher-assessed score. Any score above a 5.6 will be rounded up.

> self-assessed score*(.25)+ teacher score*(.75) = YOUR FINAL GRADE

*Example final score:*

    Self-assessed score = 5
    Teacher-assessed score = 6
    Final score = 5(.25) + 6(.75) = 5.5 = 6
