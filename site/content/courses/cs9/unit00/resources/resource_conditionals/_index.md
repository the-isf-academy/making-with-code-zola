---
title: Conditionals
type: resource
---

## Intro to conditionals

{{< tabs "code-process" >}}
{{< tab "Video Explanation" >}}
Coming soon!
{{< /tab >}}
{{< tab "Text Explanation" >}}

### Conditional code execution
One of the most powerful ways to utilize computation is to respond to differences
in the context our code is running in by changing the behavior of our code. This
might sound complicated, but as a human you are very familiar with this kind of response.

There are many situations where you change your behavior based on the environment. For
example, if it is raining outside, you wear rain boots. Otherwise, you might wear a
different kind of shoe like tennis shoes.

You probably have even more complicated environmental responses as well. For example, if
you are ordering bubble tea, your order might go like this: if the shop has taro, you get
taro in your tea. If the shop doesn't have taro but has pearls, you get pearl
in your tea. Finally, in the case that the shop doesn't have taro or pearl, you don't order
any bubble tea.

In computer science, we call this kind of behavior conditional: your code runs only in
the case that some condition is satisfied.

#### conditions

### Syntax

#### if statements

#### else statements

#### elif statements
Now that you've got some experience running Python programs, here's a brief overview of what Python does.

In the first lab, you wrote text into Python files using the text editor Atom.

{{< figure src="images/courses/cs9/unit00/00_variables_text_code.png" width="100%" title="Text in a text file" >}}

This text wasn't just any text however, it used special terms and syntax from the Python language. This is why
saving your files as `.py` files is so important - it designates what language to expect inside the file. 
{{< figure src="images/courses/cs9/unit00/00_variables_python_code.png" width="100%" title="Text interpreted as Python code in a .py file" >}}

Just like natural languages like Chinese or English, Python has rules that determine what has meaning and what doesn't
have meaning in the language. This is known as the syntax of the language. You can write whatever you want in a `.py`
file, but if it doesn't follow the rules of python syntax you will get an error when you try to run the program.

Like many natural languages, the order of statements in Python matters. Python (generally) executes statements one-by-one
from top to bottom. That's why these two snippets of code will produce different drawings despite having all the same
statements (try it out if you don't believe):
{{< columns >}}
```python
from turtle import *

forward(100)
right(45)
forward(100)
```

<--->

```python
from turtle import *

forward(100)
forward(100)
right(45)
```
{{< /columns >}}

After writing what we want our computers to do with Python syntax, we turn to a program in your computer
called Python3 (which is the program you run when you type `python homework01.py` in the Terminal). You have
to use correct Python syntax when writing code because Python3 must interpret code and translate it into
something your computer can read, often called machine language.

{{< figure src="images/courses/cs9/unit00/00_variables_machine_code.png" width="100%" title="Code translated to machine language" >}}

{{< aside >}}
Above, we said the Python *generally* executes statements one-by-one from top to bottom. The word "generally"
is necessary here because the Python3 interpreter will sometimes do things in the background to make your 
code run more efficiently. This might change the way the code is actually executed, but it shouldn't change
the functionality of your code. You can still assume that your code is being executed line-by-line.
{{< /aside >}}

Once your code is in machine language, your computer takes over to carry out the instructions you give it. In the case of the
drawing assignment, this meant showing a moving turtle drawing lines on your screen.

{{< figure src="images/courses/cs9/unit00/00_variables_turtle_square.png" width="100%" title="How your computer acts on the machine code" >}}

{{< /tab >}}
{{< /tabs >}}
