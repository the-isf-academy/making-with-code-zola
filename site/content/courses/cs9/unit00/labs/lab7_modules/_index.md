---
title: 7. Modules
type: labs
#draft: true
---

# Modules Lab

In this lab, we will learn how to organize our functions into modules. Modules are files of reusable function. You've already encountered modules before!

## [0] What is a module?
In the previous lab, we used functions to break up a big program into smaller programs. Modules do the same thing, but on a larger scale!

So let's say you wrote a function in one file. What if you want to re-use a function you wrote in a different file? Copy it over?  It feels like there should be a better way. **Today we are going to learn how to import code from one module into another.** But first, let's get some vocabulary straight:

- **All python code lives in `files` that end in `.py`.** They're just plain text files that you can edit using Atom (or Microsoft Word if you really want. Don't though. You'll regret it.)
- **Python thinks of each file as a `module`.** Each module is its own little bubble world.
- **Python thinks of each directory containing `.py` files as a `package`.** A package is a bundle of modules. So your `unit_00` directory is also a package.

## [1] Importing
When you want to use something from another module, you need to `import` it. 

We have actually already been doing this. Every one of our programs so far has started with `from turtle import *`. But what is this `turtle`? Where did it come from? 

{{< code-action "Let's use the python shell to find out more about the Turtle" >}} 

```shell
cd Destop/cs9/unit_00
python3
>>> import turtle
>>> turtle
<module 'turtle' from '.../turtle.py'>
```

See? It's a module! And it lives in a file called `turtle.py` that some people wrote for you.

```shell
>>> turtle.forward
<function forward at 0x102f90d08>
```

There's our old friend `forward()`, the function which makes the turtle walk forward. 

**There are actually three different ways to get `forward`.** 

You can import `turtle`:
```python
import turtle
turtle.forward(100)
```

Or, you can import `forward` from `turtle`:

```python
from turtle import forward
forward(100)
```

Or, you can do it the way you are used to doing it:

```python
from turtle import *
forward(100)
```

This third way means "go into the turtle module and import everything!" It's quick and easy, but it's kind of sloppy and it's not always a very good idea. 

**Imagine this scenario:**

```python
from bodily_functions import eat
from refrigerator import *
from trash_can import *

eat(chicken_sandwich)
```

You can see that the `eat` function came from `bodily_functions`, but where did that `chicken_sandwich` come from? The `refrigerator`? Or the `trash_can`? By importing just what we need from other modules, we can make it clear where everything came from, and we can make sure we don't import stuff we don't want. (What else did we import from the `trash_can`? Do we want that in our program?)

{{< checkpoint >}}
Before you go on, figure out how to open `turtle.py` on your computer using either the finder or the terminal.

- In your notebook, describe the steps you took in order to find `turtle.py`
- Take a screenshot of the `turtle.py` file and put it in your Google Drive for this class
{{< /checkpoint >}}

## [2] Finding modules
There are three places you can import modules from:

- Some modules, like `turtle`, come pre-installed with python. When you import them, python knows where to find them.
- Some modules were published online by other software developers. If you install them, you can use them too.
  Like the built-in modules, python knows where to find these when you import them.
- Finally, any modules that are in the same directory as your python file can be imported.


Now let's try importing some of the code you wrote in previous lessons. 

{{< code-action "Install" >}} `tree` to see what we're dealing with.
> **Don't forget to exit the Python shell by pressing `control+d` before entering this command! Check to make sure you see the command line prompt!**

```shell
brew install tree
```

Now, let's have a look at all your work in this class so far. We're going to show a tree of `.`, which means "here" (whatever directory you're currently in).

```shell
tree .
.
├── lab_00_terminal_adventure
│   ├── adventure
│   │   ├── seafloor
│   │   │   ├── coral_reef
│   │   │   │   ├── chest.py
│   │   │   │   └── reef.txt
│   │   │   ├── seafloor.txt
│   │   │   └── sunken_ship
│   │   │       ├── galley
│   │   │       │   └── ghost.py
│   │   │       ├── ship.txt
│   │   │       └── stateroom
│   │   │           └── desk.py
│   │   └── sinking.txt
│   └── returnToShip.py
├── lab_02.py
├── lab_02_drawing.py
├── lab_02_extension.py
├── lab_03_loops
│   ├── fibonacci_sequence.py
│   ├── geometric_sequence.py
│   └── loops_intro.py
├── lab_04_conditionals
│   ├── conditionals_modulo.py
│   └── conditionals_user_input.py
├── lab_05_while_loops
│   └── hailstone_sequence.py
└── lab_06_functions
    ├── grid.py
    └── ice_cream.py

```

From the `unit_00` folder, we can import any of these `.py` files as modules. 

If they're in the same directory (like `lab_02_drawing.py`), we can just write `import lab_02_drawing`. 

{{< code-action "Open the Python shell and try it:" >}} 

```shell
python3
>>> import lab_02_drawing
```

Fond memories. You should have seen your responsive drawing run again. This is because when you import a module, all the code in that module runs. 

What about subdirectories that contain `.py` files? Python thinks of these as packages. Remember that treasure chest from the {{< ref_lab "lab1_terminal" >}}? It's buried a few layers deep in packages, but we can get it.


{{< code-action "Trying getting the chest from the " >}} `lab_00_terminal_adventure`

```shell
>>> import lab_00_terminal_adventure.adventure.seafloor.coral_reef.chest
```

Usually we use packages to group together code that belongs together.

## [3] Drawing Package

Now we are going to download a package full of fancy drawing functions to turbocharge your turtle. 

### [Setup]

{{< code-action "Create a" >}} `lab_07_modules` **folder in your** `unit_00` **directory:**

```shell
cd ~/Desktop/cs9/unit_00
mkdir lab_07_modules
```

{{< code-action "Install the " >}} `drawing` **package using git:**
```shell
git clone https://github.com/the-isf-academy/drawing.git
```

{{< code-action "Run" >}} `tree drawing` to learn about what's included.

```shell
tree drawing
drawing
├── README.md
├── images
│   ├── dashes.png
│   ├── dots.png
│   ├── fancy_star.png
│   ├── fancy_star_basic.png
│   ├── letters.png
│   ├── perspective.png
│   └── rainbow.png
├── lines.py
├── movement.py
└── shapes.py
```
<hr>

### [Fancy Drawing]

{{< code-action "Create a " >}} `fancy_drawing.py` **file in your** `lab_07_modules` **directory.** Use this file to explore each module in the `drawing` package. 

> **Your file must include uses of at least:**
> - 2 functions from the `shapes` module
> - 2 functions from the `lines` module
> - `no_delay()` from the `movement` module
> - `restore _state_when_finished()` from the `movement` module.

{{< aside "Documentation">}}
Packages always include documentation to communicate to users how to use the included software. 
**This lab will require you to read documentation** provided in the `README.md` file. 

{{< look-action >}} **Read the [documentation](https://github.com/the-isf-academy/drawing) for examples of all the functions available in the `drawing` package.**

{{< /aside >}}



{{< code-action "Feel free to use the starter code below to get started." >}}
```python
###################
# fancy_drawing.py
# YOUR NAME
###################

from drawing.shapes import block_a, block_b
from turtle import penup, pendown, forward

def move_space():
    penup()
    forward(75)
    pendown()

block_a(100)
move_space()
block_b(100)
move_space()
block_b(100)
move_space()
block_a(100)

input()

```

{{< checkpoint >}}
In your notebook, answer the following questions:
- What are the three ways to import and use the `fancy_star` function?
- What does `with no_delay()` do?
- What does `with restore_state_when_finished()` do?
- What are 3 advantages of importing modules?
{{< /checkpoint >}}

## [4] Deliverables

{{< deliverables "For this lab, you should:" >}}
- Upload your `fancy_drawing.py` file to your Google Drive
- Hand-in your notebook with answers to the checkpoint questions
{{< /deliverables >}}
