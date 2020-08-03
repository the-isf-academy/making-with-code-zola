---
title: 1. Terminal Adventure
type: labs
---
# Into the Terminal
This lab will explore one of the most important tools we'll use all year: the Terminal. While it
may seem complicated at first, it will quickly become your go-to tool for computer science class.
The Terminal is what we'll use to navigate our filesystem, run code files, install software, and
do all kinds of other tasks.

## Dissecting the command line
We've already used a lot of commands to help us navigate Terminal. Let's take a deeper look at 
what we're actually doing when we type commands in the command line.

```shell
TEA-JWOLF:cs9 jwolf$ ls
env     unit_00
```

Lines in the command line have two parts.

{{< columns >}}

**The Prompt** `TEA-JWOLF:cs9 jwolf$` – This part is provided by the Terminal, so we don't need
to type it. The prompt can vary on different computers and shell programs, but generally it shows 
things like the machine we're using (`TEA-JWOLF`), the directory we're currently in (`cs9`), and 
the current user (`jwolf`).

<--->

**The Command** `ls` – In the line above, we're entering the `ls` command to list everything 
in the current directory.

{{< /columns >}}

### Commands
Now, let's see what goes into a command. Some commands like like `pwd` (which shows us the path
to our current location) appear solo:

```shell
TEA-JWOLF:cs9 jwolf$ pwd
/Users/jwolf/Desktop/cs9
```

### Arguments
Other commands require *arguments* that follow the command. An *arguement* is a specification for
where or what you want the command to run. For example, the `cd` command requires a path to a
directory as an arguement:

```shell
TEA-JWOLF:cs9 jwolf$ cd unit_00/
```

Some commands require multiple arguments. `mv` moves a directory or file to another location and
requires two paths as arguements:

```shell
TEA-JWOLF:cs9 jwolf$ mv file.txt unit_00/
```

### Options
Finally, the functionality of commands can often be changed with *options* which are placed between
the command and any arguments the command takes. An *option* is a minor difference in the way the 
command works. For example, the `rm` command normally removes (or deletes) a file:

```shell
TEA-JWOLF:unit_00 jwolf$ rm bad_file.txt
```

However, with the `-d` option, `rm` will also remove a directory:

```shell
TEA-JWOLF:unit_00 jwolf$ rm -d bad_directory
```

### More commands
You can learn more about the arguments and options associated with a command by googling it. If
you're interested in learning more commands, [this](https://www.codecademy.com/articles/command-line-commands) 
is a good place to start.

{{< aside >}}
From now on, we will just use `$` to represent the terminal prompt unless the path to the
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

In this lab, we are going to practice using the Terminal.

{{< code-action >}} Open a new Terminal window and enter the following commands
(Don't type the `$`.):

```shell
$ cd Destop/cs9/unit_00
$ git clone https://github.com/the-isf-academy/lab_00_terminal_adventure.git
$ ls
lab_00_terminal_adventure	 
$ cd lab_00_terminal_adventure
```

You just copied some code from GitHub onto your computer. 

{{< code-action >}} Let's have a look:

```shell
$ ls
adventure	    returnToShip.py
```

`returnToShip.py` is a runnable Python file (you can tell by the `.py` at the end). {{< code-action >}} Run it to see what happens:

```shell
$ python returnToShip.py
  Your adventure has only just begun. You are not yet ready to return
  to the ship. More secrets await you in the ocean's depths.
```

Today, you will use Terminal to explore the contents of the `adventure` directory.

Your challenge is to see if you can get the treasure, using just the Terminal.
{{< code-action >}} To get started, let's go into the `adventure` directory:

```shell
$ cd adventure
$ ls
seafloor	sinking.txt
```

`sinking.txt` is a text file, so we can read it. {{< code-action >}} Try using the `cat` command:

```shell
$ cat sinking.txt
```

You will end by running `returnToShip.py` in the `lab_00_terminal_adventure` directory.

Below are some Terminal commands which might come in handy on your adventure.

{{< expand "Terminal Commands" >}}

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


### More terminal commands
These are just for fun. There's lots more--ask your teachers!

| Command              | What it does                                 |
| --------------       | -------------------------------------------- |
| `say hello`          | Makes the computer say hello (Mac only)      |
| `cat sinking.txt | say` | Makes the computer read the text file aloud |
| `cal`                | Shows you a monthly calendar                 |
| `banner hello`       | Just try it                                  |

{{< /expand >}}
