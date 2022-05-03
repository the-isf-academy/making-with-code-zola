---
title: "3. Video Game Titles"
type: checkup
---
# Video Game Titles

In this Do Now, you must create a class with initalized parameters.  

---

## Set up

{{< code-action "First, navigate to your cs9/donows/unit_02 folder" >}} `unit_02` **folder.**

```shell
cd Desktop/cs9
cd cs9-donows-YOUR-GITHUB-USERNAME
cd unit_02
```

{{< code-action "Create a new document" >}}
```shell
atom donow3.py
```
---

## Writing the VideoGame class

It's up to you to write a class called `VideoGame` that has the following properties:
- `title`
- `genre`

Unlike the previous classes we've encountered, yours **must require it to be initilized with the two properties**. 

This will require you to initalize it like so:
```shell
>>> game1 = VideoGame("Tetris", "Puzzle")
>>> game1.title
"Tetirs"
>>> game1.genre
"Puzzle"
``` 

{{< code-action >}} **Write the `VideoGame` class in `donow3.py`.**
>> Take a look at [this](http://programarcadegames.com/index.php?chapter=introduction_to_classes&lang=en#section_12_5) resource to learn about constructors. 

{{< code-action "Test your code to ensure it works as expected." >}}

{{< deliverables "Push to Github." >}}

Push your `donow3.py` to Github.


{{< /deliverables >}}

---


### [Extension: Library of Games]

Objects, or classes, can also hold objects as parameters. For example, what if we wanted to create our own `GamesLibrary` that holds `VideoGame` objects. 

{{< code-action >}} **Create a `GamesLibrary` class that has the following features:**
- `games`: a list
- `add_game()`: adds a game to the `games` property 
- `view_games()`: prints a nicely formatted list of `games`








