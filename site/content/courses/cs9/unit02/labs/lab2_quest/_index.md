---
title: 2. Quest Lab
resources:
- name: Quest
  src: images/courses/cs9/unit02/02_02_quest_island.png
---
{{< devnote >}}
Google Doc link, bring Quest documentation into making with code?
{{< /devnote >}}

# 2. Quest Lab

## Setup

### Planning your Quest
📝 Open [this Google Doc](https://docs.google.com/document/d/1IHKx9NzngqrQr9RFKdR_ubTxFs311b8dzMOKNl63fA0/edit?usp=sharing) and make a copy for your group. Make sure everyone has access to the doc and that all their names are on it.

### Preparing your Quest
💻 Clone the Quest framework and install its requirements (no need to accept an assignment this time).

```shell
    cd ~/Desktop/cs9/unit_2
    git clone https://github.com/cproctor/quest.git quest_lab
    pip install --editable quest_lab
    cd quest_lab
```

### Starting your Quest
🌐 Open up the [Quest documentation](http://cs.fablearn.org/docs/quest)

## Questions
Write an answer to each numbered question below in your Doc.

### Part A
Quest helps you build top-down adventure games. You control a player, who walks
around and interacts with the environment, items, and other characters.

💻 To get a feel for it, we will play a few simple games. (Note: We are using the `-m` flag here to tell Python to run the `quest.examples.island` module.)

```shell
    python -m quest.examples.island
```

{{< figure src="images/courses/cs9/unit02/02_02_quest_island.png" width="400px" >}}

Take it for a spin. You can use the arrow keys or `wasd` to move around the
island but you can't walk into the ocean.

#### Q0.
Before you look at any code, make a prediction about what classes are being used in this game.

✏️ Write this as a list of at least three imagined classes,
where for each class you describe:

- The name of the class
- What it does
- What other classes it interacts with

#### Q1.
You may have noticed some of the following features.

✏️ For each, explain how the classes you imagined in **Q0** could make this happen. You can make up new classes if you need to!

- This game is made up of a bunch of little images called *sprites*. The player
  is a sprite, and each patch of background is a sprite. How could the game keep
  track of which background sprites belong where?
- The player is not allowed to walk into the ocean. How could the game enforce
  this rule?
- As the player moves around, the *viewport* scrolls, so that the player can
  never get to the edge of the screen. Which class could make this happen? What
  rule would be applied to get this behavior?

### Part B
Now we are going to read the code for the game we just played. You can either

- Open `quest/examples/island.py` in Atom
- Or read the code [on the documentation
  website](http://cs.fablearn.org/docs/quest/_modules/quest/examples/island.html#IslandAdventure)

👀 First, skim the whole file. First there are a whole bunch of import statements:

```python
    from quest.game import QuestGame
    from quest.map import TiledMap
    from quest.sprite import Background, Wall
```

Then is a helper function called `resolve_path`--you can ignore this. Next we
have a class called `IslandAdventure`, which has a bunch of properties and
methods:

```python
    class IslandAdventure(QuestGame):
        ...
```
 Finally, a statement to run the game:

```python
    if __name__ == '__main__':
        game = IslandAdventure()
        game.run()
```

#### Q2.
`IslandAdventure` is a subclass of `QuestGame`. This means
`IslandAdventure` inherits all the properties and methods from `QuestGame`.
The properties declared in `IslandAdventure` are used by `QuestGame` to change
the game's behavior.

💻 Try changing some of these values, saving the file, and running it again.

✏️ What does each of the following do?

- screen_width
- top_viewport_margin
- player_initial_x
- player_speed

#### Q3.
`QuestGame` has a bunch of methods like `setup_maps()`, `setup_walls()`,
`setup_player()`, `setup_npcs()`, and so on. Most of these do almost nothing.
The idea is that subclasses like `IslandAdventure` can override these methods
when they need to. `IslandAdventure` overrides two methods.

💻 Now play a second version of Island Adventure:

```shell
    python -m quest.examples.island_discrete
```
There is a very slight difference in the way the player moves.

✏️ Explain the difference, using the words "continuous" and "discrete" (look 'em up).Then explain how `IslandAdventureDiscrete` achieves this. What class actually determines whether movement is continuous or discrete? Finally, explain why a game might want to use discrete movement like this.

#### Q4.
Above, you looked at the classes that determine how movement works in the game. This movement functionality works for both playable and non-playable characters (NPC).

However, how does a human player control a character's movement? Where is the user interface created in the game?

✏️ Find the two functions that handle user input and describe what happens when the UP/W, DOWN/S, LEFT/A, RIGHT/D keys are pressed.

### Part C
💻 Play another sample game:

```shell
    python -m quest.examples.grandmas_soup
```
`GrandmasSoup` shows how dialogue can be used in a Quest game. There are two main classes that help manage dialogue: `Modal` and `Dialogue`.

👀 Using the source code for these samples and the [Quest documentation](http://cs.fablearn.org/docs/quest),
learn about the `Modal` and `Dialogue` classes.

#### Q5.
✏️ Describe the differences between the `Modal` and `Dialogue` classes and what each is responsible for.

Interactions in the game happen when the main `Player` collides with an `NPC`. `GrandmasSoupGame` extends the `NPC` class into two new classes: `Grandma NPC` and `Vegetable NPC`.

✏️ Describe what happens in the `Modal` and `Dialogue` classes when the player collides with one of the extended `NPC` classes.

### Part D.
💻 Play the last sample game:

```shell
    python -m quest.examples.maze
```
👀 Read the source code for the `Maze` class. Note how much of it is comments.

💻 Make some sample mazes in a terminal window by opening the python shell and running the following code:

```python
    >>> from quest.maze import Maze
    >>> m = Maze(55, 15)
    >>> m.generate()
    >>> print(m)
```
#### Q6
✏️ From reading the code and comments, what makes a maze a maze? What are its properties? What do the two parameters we pass into the `Maze` constructor mean?

The `MazeGame` doesn't change much from the basic `Game` class. However, the module also implements a `MazeMap` class, which holds most changes to run this game.

✏️ How does the `MazeMap` class work with the `Maze` class?

### Part E.
Now it’s your turn create a game! To start, pick something small, just a minor change, so you can get a feel for the framework.

Here are some example features:

* Create a confusing game where the left and right controls are flipped.
* Alter the Maze game so there is more or less treasure.
* Change the treasure sprite in the Maze game.
* Add more items to the GrandmasSoup game.

💻 Implement your game by creating a new module in the examples directory and extending one of the existing games to add a new feature.
