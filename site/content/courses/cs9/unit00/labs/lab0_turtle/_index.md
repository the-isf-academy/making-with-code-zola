---
title: 0. Set up and Turtle
type: labs
resources:
- name: GitHub
  src: images/courses/cs9/unit00/00_git_github.png

---

# Getting started
Welcome to cs9! We're glad you're here! 😄

This lab will help you get your computer set up for the class and show you how to run your
first computer program.

## Setup
To get your computer ready, we need to configure the workspace you will use for the class.

{{< aside >}}
*Hello! I'm the For Your Information Space Invader (or FyiSi for short). I'll be stopping by
every once in a while to give you some extra information about labs or the content you're
learning.  
Here's my first FYI:*

Sometimes you'll see {{< code-action >}} in a lab, this means that you
need do something that involves writing code or using your Terminal. You can use these like
little action items during labs.
{{< /aside >}}

{{< tabs "computer-setup" >}}
{{< tab "MacOS" >}}
{{< code-action >}} To begin, start your Terminal app, paste in the following line into
the window that opens, and press `return`. Enter your computer's password when the window
prompts you (you won't see any text when you're typing but that's ok).

If you run into any problems, the {{< teacher >}} know.

```shell
$ bash <(curl -sL https://raw.githubusercontent.com/the-isf-academy/courseware/master/cs9_student_setup/setup_script.sh)
```

The script installs the programs you need to write and run your code and creates a `cs9`
folder and python environment on your Desktop. This is where you'll do all the code-based
work for the class.
{{< /tab >}}

{{< tab "Windows" >}}
Coming soon!
{{< /tab >}}
{{< /tabs >}}

## Into the Terminal
Take a peek at your Desktop. You should see a new folder called `cs9` created by the configuration
script. We want to navigate to that folder using the Terminal interface to learn some Terminal skills 
that will be useful throughout the class.

### Terminal: a new user interface

You're probably used to interacting with the files in your computer through a *Graphical User Interface 
(GUI)* like Finder. Terminal allows us to interact with the files in our computer through a *Text-based 
User Interface (TUI)*. The files in our computers are organized in nested folders known as 
*directories*.

{{< code-action >}} Open a new Terminal window. Terminal opens in your `home` directory, but we will be working in the `cs9` directory.
Since the home directory holds everything we will be working with on your computer, the `cs9` directory
must be somewhere inside the `home` directory (organized as a *child directory* or *subdirectory*).

```shell
Last login: Thu Aug 15 13:57:41 on ttys008
~$
```

### What's in your home directory?

To see the files and subdirectories in the current directory, {{< code-action >}} type `ls` into the
command line and press `return`. This will list everything in the current directory.

```shell
~$ ls
Applications  Desktop  Documents  Downloads	 Library  Movies  Music	 Pictures
```

Here, you should see that `Desktop` is one of the subdirectories listed. Let's move into that
subdirectory. To do so, {{< code-action >}} type `cd Desktop` into the command line and press
`return` ("cd" stands for "change directory"). Now, list all the items in your `Desktop` 
directory using `ls`.

```shell
~$ cd Desktop
~/Desktop$ ls
Screen Shot 2019-08-15 at 12.34.48 AM.png  dobby.gif			  warsaw-boarding-pass.pdf
cs9						                   lentil loaf gravy.pdf
```

### Compare the output in the Terminal window with the Desktop shown by the GUI.

{{< code-action >}} Type `open .` to open Finder. All of the files and folders are the same!
The Terminal really does show us the same files and directories as our GUI!

{{< figure src="images/courses/cs9/unit00/00_setup_compare_terminal_finder.png" width="100%" title="Comparing Finder and Terminal files" >}}

Going back to the Terminal, we can also see that the `cs9` subdirectory is inside the
`Desktop` directory. {{< code-action >}} Change into the `cs9` directory and list what
it contains. There is another subdirectory named `unit_00`, the directory we created
for you to hold everything for Unit 0. Change into that directory and we'll be ready
to get started with some actual code!

```shell
~/Desktop$ cd cs9/
direnv: loading ~/Desktop/cs9/.envrc
direnv: export ~PATH
~/Desktop/cs9$ ls
env	unit_00
~/Desktop/cs9$ cd unit_00/
~/Desktop/cs9/unit_00$
```

{{< aside >}}
Notice how something different happened when you `cd`'d into the `cs9` directory? A piece of
software the install script installed called `direnv` just activated a virtual environment
for you Terminal session. Basically, it keeps the things you do or the software you install
for the class from affecting other parts of your computer.
{{< /aside >}}

---

## Introduction to writing code
Now that you can navigate in the Terminal, let's write some code!

{{< look-action >}} This video goes over (1) the steps to write and run a Python Turtle 
program and (2) some demos of other functions in the Turtle library [starting at 3:19 in
the video].

{{< youtube id="https://www.youtube.com/embed/sTLi5unrY6I" autoplay="true" >}}

{{< aside >}}
The {{< look-action >}} symbol is another helpful symbol to indicate that you need to do
something. This one means that there's something important for you to read or watch.
{{< /aside >}}

### Terminal Commands
As a reminder, here are some of the commands we learned for Terminal and Atom in Mac.
If you have a Windows computer, you can reference the document [here](bit.ly/windowsisf).  

| Command                 | Description |
| :---------------------- | :-----------|
*In Terminal*
| `cd Desktop/cs9/unit_00`|to change to the directory "unit_00" |
| `atom .`                |  to open Atom.   |
| `atom newfilename.py`   |  to make a new file. You can also choose to make a new file by right-clicking on the folder in atom. |
*In Atom*
| `[Insert your code]`    |  In atom, edit the file. Remember to save (`⌘S`)  the file after editing. |
*In Terminal*
| `python newfilename.py` |  to run the program. |
| `done`                  |  to end the program. |
| `↑` + `ENTER`           |  to get to the previous command you typed in terminal |

### Error and bugs
When you come across errors or bugs, do not fear! Write the issue down, and we can talk
about it during class. Try to figure out whether your bug is a:
{{< columns >}}
**Programmatic error** (which happens when the program does something different than what
you wanted. Remember that this happened when we set the angle to the wrong number)

<--->

**Syntax error** (which happens when the program crashes because the program cannot be
understood by the computer. Remember that this happened when we forgot a parentheses).

{{< /columns >}}

## Make a drawing
In class, you worked in groups to make a drawing with the python Turtle library. Here are the functions we used:

| Function |       Input      |   Example Use  | Explanation                                                                                                                      |
|:--------:|:----------------:|:--------------:|----------------------------------------------------------------------------------------------------------------------------------|
|  forward |      amount      |  forward(100)  | Moves the turtle forward by the specified amount                                                                                 |
| backward |      amount      |  backward(100) | Moves the turtle backward by the specified amount                                                                                |
|   right  | angle in degrees |    right(45)   | Turns the turtle clockwise by the specified angle                                                                                |
|   left   | angle in degress |    left(45)    | Turns the turtle counter clockwise by the specified angle                                                                        |
|   color  |     colorname    |  color("red")  | Sets the color for drawing. Use "red", "black", etc.  Here's a list of all the colors.                                           |
|   shape  |     shapename    | shape("arrow") | Should be "arrow", "classic", "turtle", or "circle"                                                                              |
|   speed  | number from 0-10 |    speed(0)    | Determines the speed at which the turtle moves around the window. 1 for slowest, 3 for normal speed, 10 for fast, 0 for fastest. |
|  pendown |       None       |    pendown()   | Puts down the turtle/pen so that it draws when it moves                                                                          |
|   penup  |       None       |     penup()    | Picks up the turtle/pen so that it doesn’t draw when it moves                                                                    |
| pensize  |       width      |   pensize(4)   | Sets the width of the pen for drawing                                                                                            |
