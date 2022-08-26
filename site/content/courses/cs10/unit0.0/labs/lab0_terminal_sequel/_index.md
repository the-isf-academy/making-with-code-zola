---
title: "0. Terminal Adventure: Sequel"
type: lab
slug: lab0_terminal_adventure_sequel
repo_url: https://github.com/the-isf-academy/lab-terminal-adventure-sequel
init_action: clone
# numberHeaders: true
# draft: true
---


# The Terminal: Reloaded
This lab will re-explore one of our most important and most used tools: the Terminal. 
The Terminal is what we use to navigate our filesystem, run code files, install software, and
do all kinds of other tasks.


## [0] Terminal Adventure Lab

The last time you ventured into the Terminal, you came away with treasure! It's time to dive back into the sea and see what's hiding.

{{< figure src="https://www.kindpng.com/picc/m/410-4102844_transparent-pirate-ship-silhouette-png-pirate-ship-drawing.png" width="75%"  >}}

{{< code-action "Open a new Terminal window and enter into the" >}} `making_with_code/cs10/unit0.0_review` **directory**

```shell
cd desktop/making_with_code/cs10/unit0.0_review
```
{{< code-action >}} **Use the `mwc` tool to clone the repo.**
```shell
mwc update
```
> *Going forward, you will be using `mwc update` to clone repositories onto your computer. No more need to `git clone`.*

{{< code-action "Let's enter the repo and then enter the Poetry shell." >}} 
> *We will be entering the Poetry shell every time we enter a repository.*

```shell
cd lab0_terminal_adventure_sequel
poetry shell
```
You should see the following after entering the Poetry shell:
```shell
Spawning shell within /Users/eqbrown/Library/Caches/pypoetry/virtualenvs/lab-terminal-adventure2-QE1DVo_2-py3.10
bash-5.1$ . /Users/eqbrown/Library/Caches/pypoetry/virtualenvs/lab-terminal-adv
enture2-QE1DVo_2-py3.10/bin/activate
(lab-terminal-adventure2-QE1DVo_2-py3.10) bash-5.1$ 
```

{{< code-action "Now take a look at what's in the repository:" >}} `ls`
```shell
kitchen	    captain.py     helpers.py
```

`captain.py` is a runnable Python file (you can tell by the `.py` at the end). *`helpers.py` provides some useful functions that are utilized in this adventure. You can just ignore it until the extension.*

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

Once you've successfully completed the adventure be sure to fill out [this Google form](https://docs.google.com/forms/d/e/1FAIpQLScjMk5bB6NCcO5r6UQlp34qoT8hLT6XTan7NTWu-ijoP6977w/viewform?usp=sf_link).

{{< /deliverables >}}

---

## [1] Extension

Delve into the code and try and learn how the Terminal Adventure works. Can you add your own feature? 

Some ideas include but are not limited to:
- generating different sandwiches depending on the ingredients in the `sandwich_maker` directory
- adding a new quest from the captain after eating the sandwich
- writing more rooms into the ship for the user to explore


{{< code-action "Expand the current Terminal Adventure!" >}} 