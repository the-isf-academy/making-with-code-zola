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
### Check system requirements
1. Go to `Settings > System > About`.
1. Check that the Edition is Windows 10.
1. Check that System type says "64-bit operating system..."

(Based on [this guide](https://www.howtogeek.com/228042/how-to-switch-from-32-bit-windows-10-to-64-bit-windows-10/))

### Enable developer tools
1. Go to `Control Panel > Programs > Turn Windows Features On Or Off`.
1. Enable the “Windows Subsystem for Linux” option in the list, and then click the “OK” button.
1. Click “Restart now” when you’re prompted to restart your computer.

### Download Ubuntu
1. After your computer restarts, open the Microsoft Store from the Start menu, and search for
“Linux” in the store. Click “Get the apps” under the “Linux on Windows?” banner.
1. Select Ubuntu.
1. click the “Get” or “Install” button.

(Based on [this guide](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/))

### Setup Ubuntu
1. Open Ubuntu once it's finished installing
1. Make a username by typing `sudo adduser your-name` and pressing enter (replace `your-name`
with your name).
1. Give this user admin privileges by typing `usermad -aG sudo your-name` and pressing enter
(again, replace `your-name`).

### Get python and pip
1. Get the programming language (Python) and package manager we'll be using for the course by
typing the following lines one by one:
    ```shell
    sudo apt-get update
    sudo apt-get install python3-tk
    sudo apt-get install python3
    sudo apt install python3-pip
    pip3 install --upgrade pip
    ```
1. Check to make sure this worked by typing `python3 -V`. If there's no output let a teacher know

### Download Xming for graphics
1. Download Xming from [this link](https://sourceforge.net/projects/xming/).
1. Install the package that downloads by double clicking on it and going through the install wizard.

### Setup your bash profile
1. Open Ubuntu.
1. Type `vim ~/.bashrc` and press enter. This will open a text file that holds configs for
your shell.
1. Go to the bottom of the file and press `i`.
1. Add the following lines to the file. Be sure to replace `YOUR_USERNAME` with the name 
you entered when you set up Ubuntu.
    ```
    export DISPLAY=:0
    cd /mnt/c/Users/YOUR_USERNAME
    ```
1. Save and close the file by typing `ESC` and then `:wq`.
1. Run `./.bashrc` in your Ubuntu window.

### Setting up files and folders for cs9
1. In your Ubuntu window, change to the Desktop using `cd Desktop`.
1. Make a cs9 folder using `mkdir cs9`.
1. Change to the directory using `cd cs9`.
1. Make a unit_00 folder using `mkdir unit_00`.

### Download Atom
1. Download Atom from [this website](https://atom.io/) and install.

([This guide](https://medium.com/@rhdzmota/python-development-on-the-windows-subsystem-for-linux-wsl-17a0fa1839d)
has instructions for installing shell commands to open files and projects in Atom)

### Download Homebrew
1. Run the following command in your Ubuntu window:
    ```shell
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
    ```

{{< aside >}}
If this website says to use Terminal, you should use Ubuntu. There will be other small differences
for Windows users that we'll explain along the way.
{{< /aside >}}
{{< /tab >}}
{{< /tabs >}}

{{< aside >}}
*Hello! I'm the For Your Information Space Invader (or FyiSi for short). I'll be stopping by
every once in a while to give you some extra information about labs or the content you're
learning.  
Here's my first FYI:*

Sometimes you'll see {{< code-action >}} in a lab. This means that you
need do something that involves writing code or using your Terminal. You can use these like
little action items during labs.
{{< /aside >}}

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
Now that you can navigate in the Terminal, let's write some code! Throughout the class, we
will be using the Python programming language to help us perform computational tasks. In
this unit, we'll be using a software library called turtle to draw things with code.

{{< look-action >}} Watch/read the explanation of how to write and run Python programs
below.

{{< aside >}}
The {{< look-action >}} symbol is another helpful symbol to indicate that you need to do
something. This one means that there's something important for you to read or watch.
{{< /aside >}}

{{< tabs >}}

{{< tab "Video Explanation" >}}

{{< youtube id="https://www.youtube.com/embed/sTLi5unrY6I" autoplay="true" >}}

{{< /tab >}}

{{< tab "Text Explanation" >}}
### Writing programs
Python programs start out as simple text files. To write a Python program, we start out
by writing a text file. During the setup, we downloaded a special text editor made for
the purpose of writing code. {{< code-action >}} Use the Terminal commands below to open
a new file in Atom:

```shell
~$ cd Desktop
~/Desktop$ cd cs9
direnv: loading ~/Desktop/cs9/.envrc
direnv: export ~PATH
~/Desktop/cs9 cd unit_00
~/Desktop/cs9/unit_00 atom first_program.py
```

This should open a new Atom window with a tab that says `first_program.py`.

Python programs consist of lines of code that tell your computer what you want it to do.
{{< code-action >}} Paste the following lines of code into the `first_program.py` file in Atom:

```python
from turtle import *

forward(50)
right(90)
forward(50)
right(90)
forward(50)
right(90)
forward(50)
right(90)

input()
```

Can you guess what these lines of code are telling the computer to draw?

### Running programs
Now that you've written a program, let's run it to see what it does!

To run Python code, we need to give our programs to a python interpretor. Fortunately,
we installed a Python interpretor in your Terminal during the setup. To use it,
you can use the command `python file-name.py`. This will read in the text file you
pass it, interpret it as a Python program, translate it into a format that your computer
can understand, and then give those instructions to your computer.

Let's try it with the program you just wrote in Atom.  
{{< code-action >}} First, save the `first_program.py` file in Atom using the `cmd-s` keys.  
Next, return to the Terminal and run the command `python first_program.py`.


What happend? Did your computer draw what you expected?

{{< code-action >}} End the program and close the turtle window by pressing `return`.

{{< aside >}}
Most files in your computer have a file type that tells your computer how to interpret them.
The file type is determined by the letters after the dot in the file name.

Notice that even though python programs are just text files, we're saving it with the `.py`
file extension. This tells our computer that this file should be interpreted as a python
file.
{{< /aside >}}

{{< /tab >}}
{{< /tabs >}}

You just ran your first Python program! Congrats!! 🎉

Before we move on, here a summary of the commands you just learned:
{{< expand "Terminal and Atom commands" >}}
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
{{< /expand >}}

## Let's draw!
Now that you've got the basics, try editing your `first_program.py` file to make it more interesting.
{{< code-action >}} Work with your group to try out some other turtle command below:

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

### Error and bugs
While trying this out, you may come across errors or bugs, do not fear! 
Write the issue down, and we can talk about it during class. Try to
figure out whether your bug is a:
{{< columns >}}
**Programmatic error** (which happens when the program does something different than what
you wanted. Remember that this happened when we set the angle to the wrong number)

<--->

**Syntax error** (which happens when the program crashes because the program cannot be
understood by the computer. Remember that this happened when we forgot a parentheses).

{{< /columns >}}

