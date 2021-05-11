---
title: 1. Uno Lab
resources:
- name: Uno
  src: images/courses/cs9/unit02/02_01_uno.jpg
---
{{< devnote >}}
CS1/CS2 links
{{< /devnote >}}

# 1. Uno Lab

## Overview
Growing up, Uno was one of my favorite card games. Everywhere I went it seemed like we ended up playing Uno – with my friends, with my family, even with my classmates.

{{< figure src="images/courses/cs9/unit02/02_01_uno.jpg" width="400px" >}}

However, when I got older I stopped liking Uno because I thought it was all random, there was no strategy to winning.

But in this lab, you are going to prove me wrong.

Your tasks:

1. Learn about how class inheritance works in Python
2. Play and redesign the uno game
3. Add special cards to make the game more interesting
4. Write a strategy to beat a random computer player

If you've never played Uno before or haven't played it in a while, you might want to try out [this online version](https://poki.com/en/g/uno-online) before you get started.

## [0] Setup

💻 **TODO:** Create an individual repository for the lab using the following links:

If you are in **CS 1**, [click here](https://classroom.github.com/a/LnM0ebqn).

If you are in **CS 2**, [click here](https://classroom.github.com/a/98E-cm7d).

💻 **TODO:** Clone your assignment repository in your `cs9` directory.

💻 **TODO:** In the lab directory, install the packages you need to run this lab by running `pip install --upgrade -r requirements.txt`.

## [1]  Classes *and* games
In this lab, we'll work to solidify our understanding of classes and objects by using a text-based game, Uno, as an example.

### More OOP in Python
To get started, we need first need to learn how to create a class in Python.

👀 **TODO:** Explore this resource: [12.5 Constructors](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_5)

Next, we need to learn about a powerful tool that can help us when we are creating classes: inheritance.

👀 **TODO:** Learn about inheritance with this resource: [12.6 Inheritance](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_6)

### Map out the Uno software
Uno is a pretty significant software project - there are more classes than you've seen before. Fortunately, [Uno's functionality is well documented](https://cs.fablearn.org/docs/uno/index.html).

🎨 **TODO:** With your new understanding of classes and inheritance, read through [the documentation](https://cs.fablearn.org/docs/uno/index.html) pages and make a model for how this implementation of Uno works.

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
💻 **TODO:** Now that you've got a model for how the Uno software should work, play through a game by running the following command in your terminal:

```shell
    python game.py
```
Was the gameplay different than you expected? Check you model to see if it still makes sense and change it up if it doesn't.

**Note:** we've given you a few different decks of cards. Start with the basic deck. We'll use the others later.

### Reskin
One potentially confusing part of the software is the [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView) class. What is it and why is it important?

In many games, it's useful to separate the logic of the game from the user interface of the game. This lets developers easily change the interface without having to mess around with the rules or state of the game. In our Uno software, [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView) does just that.

Playing around with the [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView) class will help you get a sense of how classes can interact in python. The [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView) object knows nothing about the state of the game but delivers messages to users nonetheless.

💻 **TODO:** Reskin the Uno game by changing up the messages delivered to the user in `view.py`.

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

We've already implemented some of the special cards for you. 💻 **TODO:** Try playing again, but this time use the `uno_cards_no_draw.csv` deck.

### Writing the special card functions
Pretty different right? Your job is to finish implementing the special cards by writing the code for:

- [draw_two()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.draw_two)
- [wild_draw_four()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.wild_draw_four)

💻 **TODO:** Implement the functions near the bottom of the `game.py` file in the [UnoGame](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame) class.

**Note:** you will also need to make sure the game calls these functions by adding calls to them in the [special_card_action()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.special_card_action) function.

#### Testing your functions
💻 **TODO:** You can test the `draw_two()` function by running `python test_lab.py -k draw_two`.

💻 **TODO:** You can test the `wild_draw_four()` function by running `python test_lab.py -k wild`.

#### aside: cards/reading into deck
For this implementation of the game, cards are read into the deck as entries in a csv file. Look at the `deck.py` module and you'll note that we're using pandas to read the cards  looks like those data science skills will come in handy after all!

If you are interested, you can create your own decks by writing new csv files. Have an idea for a new special card? Just create a new csv file with the name of your special card in the special column.

## [4] A winning strategy
Now that you've got a fully functional Uno game, you can start thinking about the best strategy to win games.

### Write ComputerPlayer class
In this final part of the lab, you should write an extension of the [ComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.ComputerPlayer) class which plays Uno with a strategy that you design.

**Your goal: to consistently win more than 30% of games against 3 other computer components who are using a random valid choice strategy.**

Before you jump into coding this part, you should think about the rules and mechanics of Uno. Given a hand of cards, what would make playing one card better than playing another card? You might also want to go over [inheritance](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_6) one more time as your [StudentComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.StudentComputerPlayer) class will be a child class of the [ComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.ComputerPlayer) and will inherit all its properties and functions.

💻 **TODO:** Implement your [StudentComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.StudentComputerPlayer) class in the `player.py` module.

### Test out your strategy
💻 **TODO:** Once you've written a [StudentComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.StudentComputerPlayer), you can test it by running `python test_lab.py -k strategy`
