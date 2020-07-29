---
title: 1. Types Lab
---

# Types Lab
{{< devnote >}}
replace links to isf repo <br>
fix modulo link (functions lesson in unit 0)
{{< /devnote >}}


## Part 1: Thinking about types

In this part, we'll do some thinking but no programming.

✏️ **Work with your table to fill in the following table. For each function describe what type the function would take as an input, and what type the function would return as output.**

| Function                                                         | Input type(s) | Output type |
|------------------------------------------------------------------|---------------|-------------|
| Square root of a number                                          |               |             |
| Multiplication of two numbers                                    |               |             |
| `>`                                                              |               |             |
| `not`                                                            |               |             |
| Average of a list of numbers                                     |               |             |
| A function that gives all the factors of a number                |               |             |
| A function to check if a word is a curse word                    |               |             |
| A function that assigns a friendliness score to a sentence       |               |             |
| A function that takes a website URL and returns the page content |               |             |
| A function that counts the number of sentences in a paragraph    |               |             |

You may either write this table on paper, or copy it into a document on your computer. You won't turn this in. Once you are confident in your answers (and confident everyone in your group can explain them) check with a teacher.


## Part 2: Jotto

In this part, we are going to write a bunch of functions and use them to write a
simple word game called [Jotto](https://en.wikipedia.org/wiki/Jotto). Your goal
is to guess a secret five-letter word. Each time you guess, you will be told
how many of the letters are correct (even if they're not in the right place).


{{< local >}}
{{< expand "Collaborating with GitHub" >}}

For this lab, use the following link to create a repo for your lab work. This will be a group assignment, so you will form a team with your table group and share one Github repository.


If you are in **CS 1**, [click here](https://classroom.github.com/a/r13vhXjj).

If you are in **CS 2**, [click here](https://classroom.github.com/a/C8pBPH32).

💻 **Clone the lab repo into your `unit_01` directory and `cd` inside.**

This lab will probably be the first time you use Github as a team. The basic workflow is still the same, with one slight change:

+ `git pull` to get any new changes from the Github repo
+ `git status` to determine what has change
+ `git add` to add the files you've edited
+ `git commit` to write a message about what you've changed
+ `git push` to push your changes to Github

Because multiple people will be working on the same project, you will not be the only one changing the project. This means that sometimes there will be code on Github which you do not have in your local repository.

When you begin working on a project after taking a break and before you begin the workflow above, use git pull to pull any new changes from Github to your local repository.

💻 **Have one member of your group make a change to the helper_functions.py file and then make sure everyone can get the changes in their local repositories**

If you've already got code written, this will merge your code with code your teammates put on GitHub. Sometimes, changes to your teammates' code will conflict with the changes you made. In this case, you'll need to use Atom to select which changes you want to use.

You will likely run into this over the course of this lab. Try it out on your own, and let the teaching team know if you get stuck.

{{< /expand >}}


{{< expand "Writing the game" >}}

The game itself is in `lab_01_01.py`, and is coded in just a dozen lines. The reason this is so short is that it relies on some powerful helper functions defined in `helper_functions.py`. This is where you come in! It's your job to complete these help functions. Once you complete them, `lab_01_01.py` should work.

💻 **Collaborate with each member of your group to write each function in `helper_functions.py`. Once your group has come to a consensus on a function and tested your solution, one member will push their code to Github. Then, everyone else can use git pull to get the code in your local lab directory.**

Also provided is `test_helper_functions.py`, which runs automated tests on your helper functions. Don't bother running `lab_01_01.py` until all these tests pass.

{{< /expand >}}


{{< expand "Note: Reading data from files" >}}

This game requires a list of words. We could copy and paste them into our Python file, but the word list contains the 10,000 most common English words. That would create a huge mess. A much better idea is to keep our data in a separate file, and to read it as part of our Python program.

There are a lot of different ways to read files, but one thing to keep in mind is that just about all the data files we will use in class are just plain text.

In this lab, we use an object called `Path` from [pathlib](https://docs.python.org/3/library/pathlib.html), which represents a file system path (something like "~/Desktop/cs9/unit_01/") Paths can point to files or directories. `Path` objects can do all kinds of neat tricks, like moving files, copying them, checking what they contain, and reading their contents. In this lab, you are given the following function:

```python
from pathlib import Path

    def get_words():
    filename = "10k_english_words.txt"
    return Path(filename).read_text().split()
```

It just reads the contents of the file "10k_english_words.txt" as a really long string, and then splits it into separate strings. Try opening "10k_english_words.txt" in Atom and you'll see it's just a text file with one word per line.

{{< /expand >}}


{{< expand "Using functions to transform and filter lists" >}}

One common use of functions in functional programming is to transform each item in a list into something else. For example, if we have the following super-annoying function, we might want to use it to transform a whole lot of messages.

```python
def make_enthusiastic(message):
    return "{}!!!".format(message)
```

We can use the following structure, called a list comprehension. (Note: There's a [video about lists](https://vimeo.com/367070978) that explains these ideas.)

```shell
>>> boring_messages = ["hello", "so bored", "why am I here"]
  >>> [make_enthusiastic(message) for message in boring_messages]
  ["hello!!!", "so bored!!!", "why am I here!!!"]
```

In English, this says: replace each `message` in `boring_messages` with `make_enthusiastic(message)`. By the way, message is just a variable name. It would work the same with a different name:

```shell
>>> boring_messages = ["hello", "so bored", "why am I here"]
  >>> [make_enthusiastic(m) for m in boring_messages]
  ["hello!!!", "so bored!!!", "why am I here!!!"]
```

You can also use list comprehensions to filter out items from a list. If we have the following function (remember [modulo]()?)

```python
def is_even(number):
  return number % 2 == 0
```

then we can get just the even numbers in a list:

```shell
>>> numbers = [1,2,3,4,5,6,7,8,9]
  >>> [n for n in numbers if is_even(n)]
  [2,4,6,8]
```

Again, practice reading this in English: Keep each `n` in `numbers` if it's even. Finally, you can write list comprehensions which transform and filter at the same time:

```shell
>>> [make_enthusiastic(n) for n in range(10) if not is_even(n)]
```

🔮 **Can you predict what the result will be?**

{{< /expand >}}
