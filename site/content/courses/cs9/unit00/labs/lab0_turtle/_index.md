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
