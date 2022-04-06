---
title: 2. Uno Lab
resources:
- name: Uno
  src: images/courses/cs9/unit02/02_01_uno.jpg
---
{{< devnote >}}
CS1/CS2 links
{{< /devnote >}}

# Uno Lab

## Overview
Growing up, Uno was one of Mr. Wolf's favorite card games. Everywhere he went it seemed like we ended up playing Uno – with his friends, with his family, even with his classmates.

{{< figure src="images/courses/cs9/unit02/02_01_uno.jpg" width="400px" >}}

However, when he got older he stopped liking Uno because he thought it was all random, there was no strategy to winning.

But in this lab, you are going to prove him wrong.

Your tasks:

1. Learn about how class inheritance works in Python
2. Play and redesign the uno game
3. Add special cards to make the game more interesting
4. Write a strategy to beat a random computer player

If you've never played Uno before or haven't played it in a while, you might want to try out [this online version](https://poki.com/en/g/uno-online) before you get started.

## [0] Setup

{{< code-action >}} **In your `cs9/unit_02` directory, clone the `lab-uno` repository inside it.**

```shell
cd cs9/unit_02
git clone https://github.com/the-isf-academy/lab-uno-YOUR-GITHUB-USERNAME.git
```

{{< code-action >}} **In the lab directory, install the packages you need to run this lab by running `pip install --upgrade -r requirements.txt`.**

## [1]  Classes *and* games
In this lab, we'll work to solidify our understanding of classes and objects by using a text-based game, Uno, as an example.

### More OOP in Python
To get started, we need first need to learn how to write a class in Python.

👀 Explore the following resources: 
- Creating a Class: [12.5 Constructors](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_5)
- Inheritance: [12.6 Inheritance](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_6)

### Modeling Inheritance 

Let's consider our model of a video game character from the bank lab. 

{{< figure src="images/courses/cs9/unit02/02_class_model_01.png" width="400px" >}}

Imagine our game has two types of characters: a player character and a non-playable character (NPC). Both types of characters should have the same properties and methods as the base `Character` class, but each will have additional unique attributes. For this, we can utilize inheritance.  


{{< figure src="images/courses/cs9/unit02/02_03_uno_inheritance_model.jpg" width="600px" >}}
*Note: the arrows signify the direction of the inheritance* 

Both the `Player` class and the `NPC` object will inherent the characteristics from the `Character` class and extend it to include additional features. 


### Map out the Uno software
Uno is a pretty significant software project - there are more classes than you've seen before. Fortunately, [Uno's functionality is well documented](https://cs.fablearn.org/docs/uno/index.html).

{{< write-action >}} **With your new understanding of classes and inheritance, read through [the documentation](https://cs.fablearn.org/docs/uno/index.html) pages and draw a model with your partner for how this implementation of Uno works.**

For your reference, Uno has the following classes. Make sure your model includes each of them.

- [Game](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame)
- [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView)
- [Card](https://cs.fablearn.org/docs/uno/card.html#card.Card)
- [Deck](https://cs.fablearn.org/docs/uno/deck.html#deck.Deck)
- [Player](https://cs.fablearn.org/docs/uno/player.html#player.Player)
    - [HumanPlayer](https://cs.fablearn.org/docs/uno/player.html#player.HumanPlayer)
    - [ComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.ComputerPlayer)
        - [RandomComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.RandomComputerPlayer)
        - [StudentComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.StudentComputerPlayer)


## [2] Let's play Uno!
The rules of Uno are pretty simple: players take turns trying to play cards from their hand. You can play a card if its color or value matches the color of value of the last card that was played. If you can't play a card, you have to draw a card. The first player to play all their cards wins.

If you're interested, you can find the [full rules of Uno here](http://play-k.kaserver5.org/Uno.html). Our implementation varies slightly. Can you identify the differences?

### Play through
{{< code-action >}} **Now that you've got a model for how the Uno software should work, play through a game by running the following command in your terminal:**

```shell
python game.py
```
*Note: we've given you a few different decks of cards. Start with the basic deck. We'll use the others later.*

Was the gameplay different than you expected? Check you model to see if it still makes sense and change it up if it doesn't.


### Reskin
One potentially confusing part of the software is the [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView) class. What is it and why is it important?

In many games, it's useful to separate the logic of the game from the user interface of the game. This lets developers easily change the interface without having to mess around with the rules or state of the game. In our Uno software, [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView) does just that.

Playing around with the [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView) class will help you get a sense of how classes can interact in python. The [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView) object knows nothing about the state of the game but delivers messages to users nonetheless.

{{< code-action >}} **Reskin the Uno game by changing up the messages delivered to the user in `view.py`.**

Maybe you want to translate the game into Chinese or make the game have an attitude. You could even try writing the game to speak in the voice of one of your favorite characters (*"Aye Aye, Player 1, two Krabby Patties comin right up for Player 2!"*).

## [3] Amp it up: special cards
Now that you're starting to get the hang of the game, let's make it a little more interesting with special cards.

### Special cards
Uno would be pretty boring if you just went around in a circle matching colors and numbers. Fortunately for you, dear player, Uno has special cards that make the game more interesting:

- **reverse:** changes the direction of play from clockwise to counterclockwise or vice versa
- **skip:** skips the next player's turn
- **wild:** can be played on any card and lets the player call the color to be played next
- **draw-two:** forces the next player to draw two cards (they still get a turn)
- **wild-draw-four:** the current player calls the color *and* the next player has to draw 4 cards

Other than the wild cards, all of the special cards have colors and must be played following the color/value matching rule of the game.

We've already implemented some of the special cards for you. 

{{< code-action >}} **Try playing again, but this time use the `uno_cards_no_draw.csv` deck.**

### Writing the special card functions
Pretty different right? Your job is to finish implementing the special cards by writing the code for:

- [draw_two()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.draw_two)
- [wild_draw_four()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.wild_draw_four)

{{< code-action >}} **Implement the `draw_two()` and `wild_draw_four()` functions  near the bottom of the `game.py` file in the [UnoGame](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame) class.**

  - **Note:** you will also need to make sure the game calls these functions by adding calls to them in the [special_card_action()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.special_card_action) function.

{{< code-action >}} **Testing your functions by running the following scripts**
- You can test the `draw_two()` function by running `python test_lab.py -k draw_two`.
- You can test the `wild_draw_four()` function by running `python test_lab.py -k wild`.


{{< expand "Reading into the Deck" >}}
For this implementation of the game, cards are read into the deck as entries in a csv file. Look at the `deck.py` module and you'll note that we're using pandas to read the cards  looks like those data science skills will come in handy after all!

If you are interested, you can create your own decks by writing new csv files. Have an idea for a new special card? Just create a new csv file with the name of your special card in the special column.
{{</expand>}}

## [4] A winning strategy
Now that you've got a fully functional Uno game, you can start thinking about the best strategy to win games.

### Write ComputerPlayer class
In this final part of the lab, you should write an extension of the [ComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.ComputerPlayer) class which plays Uno with a strategy that you design.

**Your goal: to consistently win more than 30% of games against 3 other computer components who are using a random valid choice strategy.**

Before you jump into coding this part, you should think about the rules and mechanics of Uno. Given a hand of cards, what would make playing one card better than playing another card? You might also want to go over [inheritance](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_6) one more time as your [StudentComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.StudentComputerPlayer) class will be a child class of the [ComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.ComputerPlayer) and will inherit all its properties and functions.

{{< code-action >}} **Implement your [StudentComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.StudentComputerPlayer) class in the `player.py` module.**

{{< code-action >}} **Test your strategy by running `python test_lab.py -k strategy`**

## Deliverables
For this lab, you should push your `lab-uno` repository containing updates to the following files:
  - `view.py` 
  - `game.py`
  - `player.py`

