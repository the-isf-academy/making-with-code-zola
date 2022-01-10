---
title: -1. Jupyter Notebooks 
type: checkup
# draft: True
---
## Do Now: Checking Types

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