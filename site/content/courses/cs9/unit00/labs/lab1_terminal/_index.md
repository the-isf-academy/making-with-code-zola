---
title: 1. Terminal Adventure
type: lab
slug: lab1_terminal_adventure
repo_url: https://github.com/the-isf-academy/lab-terminal-adventure
init_action: clone
numberHeaders: true
draft: true

---
# Into the Terminal
This lab will explore one of the most important tools we'll use all year: the Terminal. While it
may seem complicated at first, it will quickly become your go-to tool for computer science class.
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


{{< code-action "Open a new Terminal window and enter each command with a " >}} `$` **one by one.**
Just be sure you do not type the `$`.

```shell
$ cd Desktop/cs9/unit_00
$ git clone https://github.com/the-isf-academy/lab_00_terminal_adventure.git
$ ls
lab_00_terminal_adventure	 
$ cd lab_00_terminal_adventure
```

You just copied some code from GitHub onto your computer. 

{{< code-action "Let's have a look:" >}} 

```shell
$ ls
adventure	    returnToShip.py
```

`returnToShip.py` is a runnable Python file (you can tell by the `.py` at the end). 

{{< code-action "Run it to see what happens:" >}} 

```shell
$ python returnToShip.py
  Your adventure has only just begun. You are not yet ready to return
  to the ship. More secrets await you in the ocean's depths.
```

{{< aside "Your challenge is to see if you can get the treasure, using just the Terminal" >}}

Use Terminal to explore the contents of the `adventure` directory.

{{< /aside >}}

<hr>


{{< code-action "Begin by going into into the" >}}  `adventure` **directory:**

```shell
$ cd adventure
$ ls
seafloor	sinking.txt
```

`sinking.txt` is a text file, so we can read it. 

{{< code-action "Try using the " >}} `cat` **command:**

```shell
$ cat sinking.txt
```
---

### [Treasure]

{{< figure src="https://sealifeart.co.uk/wp-content/uploads/2019/11/treasure-chest-drawing.jpg" width="50%"  >}}

{{< deliverables "You will end this lab by collecting the treasure!" >}}

Continue exploring into the depths of the sea to find it.

Return to the `lab_00_terminal_adventure` directory and run the `returnToShip.py` file to see if you were successful. If you were unable to escape the monster, try again! 

Before moving on, check in with a teacher and answer the following prompts in your notebook:
- What are 3 functions of the Terminal?
- Compare navigating the file system via the Terminal v. the Finder. 


{{< /deliverables >}}

---

## Terminal Commands
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


### [More terminal commands]
These are just for fun. There's lots more--ask your teachers!

| Command              | What it does                                 |
| --------------       | -------------------------------------------- |
| `say hello`          | Makes the computer say hello (Mac only)      |
| `cat sinking.txt | say` | Makes the computer read the text file aloud |
| `cal`                | Shows you a monthly calendar                 |
| `banner hello`       | Just try it                                  |

