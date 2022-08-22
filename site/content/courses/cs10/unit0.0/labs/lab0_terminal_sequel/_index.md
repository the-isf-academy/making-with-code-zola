---
title: "0. Terminal Adventure: Sequel"
type: lab
slug: lab1_terminal_adventure
repo_url: https://github.com/the-isf-academy/lab-terminal-adventure
init_action: clone
# numberHeaders: true
draft: true

---
# The Terminal: Reloaded
This lab will re-explore one of our most important and most used tools: the Terminal. 
The Terminal is what we'll use to navigate our filesystem, run code files, install software, and
do all kinds of other tasks.


{{< aside "FYI" >}}
In this lab, we will just use `$` to represent the terminal prompt unless the path to the
current directory is important. If you see this in the lab:
```shell
$ ls
some-directory some-file.txt
```
but your computer shows something like this:
```shell
COMPUTER: terminal_lab username$ ls
some-directory some-file.txt
```
don't worry. As long as you see the `$` at the end, it means you can put in new commands to your
Terminal.

{{< /aside >}}


## Terminal Adventure Lab

The last time you ventured into the Terminal, you came away with treasure! It's time to dive back into the sea and see what's hiding.

{{< figure src="https://www.kindpng.com/picc/m/410-4102844_transparent-pirate-ship-silhouette-png-pirate-ship-drawing.png" width="75%"  >}}

{{< code-action "Open a new Terminal window and enter each command with a " >}} `$` **one by one.**
Just be sure you do not type the `$`.

```shell
$ cd Desktop/mwc/cs9/unit_00
$ git clone https://github.com/the-isf-academy/lab_00_terminal_adventure.git
$ ls
lab_00_terminal_adventure	 
$ cd lab_00_terminal_adventure
```

You just copied some code from GitHub onto your computer. 

{{< code-action "Let's have a look:" >}} 

```shell
$ ls
kitchen	    returnToShip.py
```

`captain.py` is a runnable Python file (you can tell by the `.py` at the end). 

{{< code-action "Run it to see what happens!" >}} **You will end this lab by successfully making a sandwich!** Explore the corners of the kitchen to find the necessary supplies.

{{< figure src="https://www.justonecookbook.com/wp-content/uploads/2020/07/Wanpaku-Sandwich-4986-I-1.jpg" width="75%"  >}}

### [Terminal Commands]
Below are some Terminal commands which might come in handy on your adventure.


| Command              | What it does                                 |
| --------------       | -------------------------------------------- |
| `ls`                 | List what's in the current directory.        |
| `cd ~`               | Go to your home directory                    |
| `cd somewhere`       | Go to `somewhere`                            |
| `cd ..`              | Go to the parent directory                   |
| `open file.txt`      | Opens `file.txt` with its default program    |
| `cat file.txt`       | Prints out the contents of `file.txt`        |
| `python x.py`        | Runs the Python program `x.py`               |
| `mv old.txt new.txt` | Renames a file from `old.txt` to `new.txt`. Also works for directories. |
| `mv file.txt dir`    | Moves a file to directory `dir`.             |
| `mv dir1 dir2`       | Moves `dir1` to `dir2` or renames if `dir2` doesn't exist.          |
| `cp old.txt new.txt` | Copy a file from `old.txt` to `new.txt`.     |
| `mkdir bag`          | Creates a new directory called `bag`     |
| `pwd`                | Prints the path to where you are in the filesystem |
| `rm file.txt`        | removes (deletes) the file `file.txt`        |
| `rm -d dir`          | removes (deletes) the directory `dir`        |
| `rm -r dir`          | recursively removes (deletes) the directory `dir` and all subdirectories and files within that directory. **Be careful, this is a powerful tool!** |

---

### [Deliverables]


{{< deliverables "Congrats on completing your adventure!" >}}  

Once you've successfully completed the adventure be sure to fill out [this Google form](xxx).

{{< /deliverables >}}

---

## [1] Extension



Delve into the code and try and learn how the Terminal Adventure works. Can you add your own feature? Can you create a new adventure from scratch? 

Create your own Terminal Adventure! 