---
title: 3. Summary Statistics Lab
resources:
---

# Summary Statistics Lab
In this lab, you will write algorithms to calculate statistics about datasets.
This will help us analyze data to answer our research questions.

## A. Setup
First, let's do some setup for this lab.

### Cloning your repository
As always, we'll start by cloning your lab repo from Github.

{{< code-action >}} Starter code for the lab is provided in the
`lab-sumstats` repo. Download it *onto your laptop*.

```shell
$ cd cs9/unit_01
$ git clone https://github.com/the-isf-academy/lab-sumstats-YOUR-GITHUB-USERNAME.git
```

### Setup Jupyter Notebooks
`cd` into your lab directory (`cd lab-sumstats-USERNAME`) and you'll notice a
new type of file: `.ipynb`.

These files are used with Jupyter notebook, a new tool you'll be learning to
help with the data science unit.

{{< code-action >}} Let's install and setup Jupyter on your computer:

{{< tabs "jupyter-setup" >}}
{{< tab "MacOS" >}}
You can install Jupyter (and some helpful extensions) using pip in the Terminal:

    $ pip install --upgrade -r requirements.txt
    $ jupyter contrib nbextension install --user
    $ jupyter nbextension enable toc2/main && jupyter nbextension enable collapsible_headings/main && jupyter nbextension enable hide_input/main && jupyter nbextension enable varInspector/main && jupyter nbextension enable hinterland/hinterland && jupyter nbextension enable python-markdown/main && jupyter nbextension enable spellchecker/main && jupyter nbextension enable exercise2/main

{{< /tab >}}
{{< tab "Windows" >}}

You can install Jupyter using pip in Ubuntu:

    $ sudo apt update
    $ sudo apt install python3-pip
    $ pip3 install --upgrade pip
    $ pip3 install --upgrade --user -r requirements.txt
    $ vim ~/.bashrc

Inside bashrc, scroll to the very end of the document. Press `I`.
Then add:

    alias jupyter-notebook="~/.local/bin/jupyter-notebook --no-browser"

Once completed, press `ESC` button.

    $ source ~/.bashrc

Now, install some extensions to make your notebooks nicer:

    $ jupyter-notebook  nbextension enable toc2/main && jupyter-notebook nbextension enable collapsible_headings/main && jupyter-notebook nbextension enable hide_input/main && jupyter-notebook nbextension enable varInspector/main && jupyter-notebook nbextension enable hinterland/hinterland && jupyter-notebook nbextension enable python-markdown/main && jupyter-notebook nbextension enable spellchecker/main && jupyter-notebook nbextension enable exercise2/main

{{< /tab >}}
{{< /tabs >}}


## B. Introducing: Jupyter notebooks
Jupyter notebooks are a special kind of programming environment that let
you write and run snippets of code in the same interface. This interface is a
powerful tool for data science because it allows you
to work on Python scripts in finer detail. This will help you clean, analyze,
and visualize data without having to re-run entire Python scripts.

{{< tabs "jupyter-intro" >}}
{{< tab "MacOS" >}}
To open a notebook, you will need to start a Jupyer server from your terminal:

    jupyter notebook
    
{{< /tab >}}
{{< tab "Windows" >}}
To open a notebook, you will need to start a Jupyer server from Ubuntu:

    jupyter-notebook

{{< /tab >}}
{{< /tabs >}}

The best way to understand Jupyter is just to try it out.

{{< code-action >}} Start a Jupyer server in your terminal. In the web browser
window that pops up, click on the file `jupyter_intro.ipynb`.

{{< code-action >}} Walk through the intro to learn how to use Jupyter.

## C. Summary Statistics
How do you make sense of lots of data? Let's summarize it with statistics!

{{< code-action >}} Open the `sumstats.ipynb` lab in Jupyter using the window
that popped up in your web browser. Complete the lab in the Jupyter notebook.

{{< write-action >}} Follow along answering the questions in your Google Doc
checkpoints sheet.

*Each person should work on their own lab and checkpoint worksheet, but you can
work together in groups to complete them.*

## D. Deliverables
For this lab, you should submit the following...

- Your `sumstats.ipynb` file with code for each of the following functions:
    - `calculate_mean()`
    - `calculate_median()`
    - `calculate_mode()`
    - `calculate_IQR()`
- Your Google Doc with responses to the checkpoint questions


