---
title: 2. Uno Lab
resources:
- name: Uno
  src: images/courses/cs9/unit02/02_01_uno.jpg
# draft: true
---

# Uno Lab

In this lab, you are going to go behind the scenes of the classic card game, Uno.


{{< figure src="images/courses/cs9/unit02/02_01_uno.jpg" width="400px" >}}

Your tasks:

0. Learn about how class inheritance works in Python
0. Add special cards to make the game more interesting
0. Write a random strategy for a computer player

## [0] Let's Play Uno

🃏 **Let's start by playing the classic card game, Uno.** As your playing, consider the different components and mechanics of the game. 

{{< checkpoint >}}
In your group, complete the worksheet. 
{{< /checkpoint >}}

---

## [1] Setup

Now that you've got a model for how the Uno software should work, let's delve into the code.

{{< code-action >}} **In your `cs9/unit_02` directory, clone the `lab-uno` repository inside it.**

```shell
cd cs9/unit_02
git clone https://github.com/the-isf-academy/lab-uno-YOUR-GITHUB-USERNAME.git
```

{{< code-action >}} **Install the packages you need to run this lab:**
```shell
cd lab-uno-YOUR-GITHUB-USERNAME
pip3 install --upgrade -r requirements.txt
```

---


### [Documentation]

Uno is a pretty significant software project - there are more classes than you've seen before. Fortunately, [Uno's functionality is well documented](https://cs.fablearn.org/docs/uno/index.html).

- [Game](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame)
- [View](https://cs.fablearn.org/docs/uno/view.html#view.TerminalView)
- [Card](https://cs.fablearn.org/docs/uno/card.html#card.Card)
- [Deck](https://cs.fablearn.org/docs/uno/deck.html#deck.Deck)
- [Player](https://cs.fablearn.org/docs/uno/player.html#player.Player)
    - [HumanPlayer](https://cs.fablearn.org/docs/uno/player.html#player.HumanPlayer)
    - [ComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.ComputerPlayer)
        - [RandomComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.RandomComputerPlayer)
        - [StudentComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.StudentComputerPlayer)

---

## [2] Play Test


{{< code-action >}} **Play through Uno in your Terminal.** Start with the "basic deck".

```shell
python3 game.py
```
> If you're interested, you can find the [full rules of Uno here](http://play-k.kaserver5.org/Uno.html). Our implementation varies slightly. Can you identify the differences?

🤔 Was the gameplay different than you expected? 

---


### [Special Cards]

Uno would be pretty boring if you just went around in a circle matching colors and numbers. Fortunately, **Uno has special cards that make the game more interesting:**

- **reverse:** changes the direction of play from clockwise to counterclockwise or vice versa
- **skip:** skips the next player's turn
- **wild:** can be played on any card and lets the player call the color to be played next
- **draw-two:** forces the next player to draw two cards (they still get a turn)
- **wild-draw-four:** the current player calls the color *and* the next player has to draw 4 cards

Other than the wild cards, all of the special cards have colors and must be played following the color/value matching rule of the game.

{{< code-action >}} **Try playing again, but this time use the select the "special no draw deck".**
> This deck includes the reverse, skip, and wild cards. 


---

## [3] Implement Draw Cards

Your version of Uno is almost complete. **All you need to do is finish the special cards by writing the code for:**

- [draw_two()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.draw_two)
- [wild_draw_four()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.wild_draw_four)

> This deck can be played by selecting "special with draw deck" from the game menu.

### [Draw Two]

{{< code-action >}} **Implement the `draw_two()` method  near the bottom of the `game.py` file in the [UnoGame](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame) class.**

{{< code-action >}} **Add the function calls to the [special_card_action()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.special_card_action) method.**

{{< code-action >}} **Test your method by running the test script:`python3 test_lab.py -k draw_two`.**
> If successful, you will see a message like so: 
> ```shell
> Ran 1 test in 0.009s
>
>OK
>```
---

### [Wild Draw Four]

{{< code-action >}} **Implement the `wild_draw_four()` method in the [UnoGame](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame) class.**

{{< code-action >}} **Add the function calls to the [special_card_action()](https://cs.fablearn.org/docs/uno/game.html#game.UnoGame.special_card_action) method.**

{{< code-action >}} **Test your method by running the test script: `python3 test_lab.py -k wild`.**
> If successful, you will see a message like so: 
> ```shell
> Ran 1 test in 0.009s
>
>OK
>```

---

## [4] AI: Random Strategy

Currently the computer strategy is quite simple: 
- when it chooses a card, it picks the last card in its hand (regardless if it's valid)
- when its asked to choose a color, it always chooses red
  
**Let's make a slightly more competitive computer by introducing randomness.** 

It's up to you to extend the [`ComputerPlayer`](https://cs.fablearn.org/docs/uno/player.html#player.ComputerPlayer) class and complete the `RandomComputerPlayer` class:

**You will need to override the following methods of `RandomComputerPlayer` with the correct functionality:**
- `choose_color()` - random chooses red, green, blue, or yellow
- `choose_card()` - randomly selects a valid card from its hand if a valid card exists


{{< code-action >}} **Finish `RandomComputerPlayer` to implement a random strategy.**
> You may want to read more about [inheritance](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_6).

{{< code-action >}} **Test your implementation by playing Uno without any human players and selecting "random" strategy.** 


---

## [5] Deliverables

{{< deliverables "Push to Github." >}}

For this lab, you should push your `lab-uno` repository containing updates to the following files:
  - `game.py`
  - `player.py`

{{< /deliverables >}}

---


## [6] Extension:

Now that you've got a fully functional Uno game, let's expand its functionality. 

### [A Wining Strategy]

🤔 **Start thinking about the best strategy to win games.**  Consider the rules and mechanics of Uno. Given a hand of cards, what would make playing one card better than playing another card? 

**Your goal: write a strategic computer that consistently wins more than 30% of games against 2 other computer players who are using a random valid choice strategy.**

{{< code-action >}} **Implement the [StrategicComputerPlayer](https://cs.fablearn.org/docs/uno/player.html#player.StudentComputerPlayer) class in the `player.py` module.**

{{< code-action >}} **Test your strategy by running `python test_lab.py -k strategy`**

---

### [Advanced Deck Building]

For this implementation of the game, cards are read into the deck as entries in a csv file. Look at the `deck.py` module and you'll note that we're using pandas to read the cards  looks like those data science skills will come in handy after all!

{{< code-action >}} **Create your own deck and add a new special card by writing new a csv file.** Just create a new csv file with the name of your special card in the special column.

{{< code-action >}} **Implement your special card in the `UnoGame` class.**