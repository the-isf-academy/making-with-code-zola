---
title: Initial Setup
# numberHeaders: true
weight: -1
---

# Initial setup

**Welcome! These instructions will help you get your computer set up for the class.**
If you get stuck or are unsure what to do, ask {{< teacher >}}. Everyone's system is 
different, so the initial setup sometimes needs some TLC. 
*You should only ever have to run these instructions once.*

---

## Github

Github is a hosting service for code. It allows users to collaborate on projects and track versions of their code over time. We will be using Github to distrbute code to students and for students to submit their work.

{{< code-action >}}
**Sign up for a Github account by going to [this](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home) link.**

{{< figure src="https://github.githubassets.com/images/modules/logos_page/Octocat.png" width="25%" alt-text="Python Turtle Graphics" >}}
- Be sure to use your ISF student email. 
- You will be asked to create a Github username. Do NOT use your student ID number and make sure it is school appropriate.  

---

## Installing Python
To get your computer ready, we need to configure the workspace you will use for the class. **Select the tab for your operating system and follow the instructions.** Please let {{< teacher >}} know if you run into any issues. 


{{< tabs "computer-setup" >}}
{{< tab "MacOS" >}}

(0) **Start by installing the latest version of Python.** [Open this link](https://www.python.org/downloads/), click "Download Python," and follow the installation instructions.


(1) **Once the installation finishes, you will see a Finder window showing what was installed**. 
(If you closed the window, open Finder, click on "Applications," and then "Python 3.10" (or whatever version of Python you just installed).


(2) **Check Python installed successfully by typing `python --version` into Powershell.** You should see a version number above `3.10`.

(3) **Double-click on "Install Certificates.command".** This will will open a Terminal window and run a bunch of commands. Once you see `[Process completed]`, you may close the window.

(4) **Double-click on "Update Shell Profile.command".** Each of these will open a Terminal window and run a bunch of commands. Once you see `[Process completed]`, you may close the window.


{{< aside >}}
**If you see a red "Permission denied" error message when running "Install Certificates.command"**:
- open a Terminal window and run **`sudo "/Applications/Python 3.10/Install Certificates.command"`** 
- You will be asked for an administrator password; you won't see any letters appearing as you enter the password. This is a security feature.
{{</ aside >}}

{{< /tab >}}

{{< tab "Windows" >}}


(0) **Start by installing the latest version of Python.** [Open this link](https://www.python.org/downloads/), click "Download Python," and follow the installation instructions.
  - Make sure you select `INSERT THING`

(1) **Open Windows Powershell**. We will be using this application every class. We suggest you pin it to your toolbar.

(2) **Check Python installed successfully by typing `python --version` into Powershell.**
> You should see a version number above `3.10`


{{< aside >}}
Whenever this website says to use Terminal, you should use Windows Powershell. There will be other small differences for Windows users that we'll explain along the way.
{{< /aside >}}

{{< /tab >}}
{{< /tabs >}}

## Install MWC

`mwc` is a special program we wrote for this class which will help you set up your assignments. 

{{< code-action "Open Terminal and run the following command." >}}
```shell
pip3 install making-with-code-cli
```

{{< aside "If the install failed..." >}}

{{< code-action "Copy and paste each command, one at a time, into the Terminal." >}} 
- `sudo pip3 install making-with-code-cli` or 
- `pip3 install --user making-with-code-cli`

Still no luck? Talk to {{< teacher >}}. 
{{</ aside >}}

{{< code-action "Check mwc installed successfully by checking the version number." >}} You should see a version number above 0.0.5, such as `MWC 0.0.53`.
```shell
mwc version
```

---

## Configure MWC

{{< code-action "Run the below command to begin the full setup." >}} This will install a few packages onto your computer. This may take up to 30 minutes to complete. Don't worry, you can still use your computer and have it running in the background.
```shell
mwc setup
```
You will be asked some questions to finish the setup process. **We suggest using the default values in the square brackets, `[]`. You can select the default value with `return`.**

{{< figure src="images/courses/cs9/unit00/0_initial_setup0.png" width="100%" alt-text="mwc setup" >}}

**You will be asked the following questions to finish the setup process:**

0. "What is your MWC username?" - Use your Github username.
0. "Where do you want to save your MWC work?" - we suggest using the default. 
0. "What's the URL of your Making With Code website?" - use the default value. 
0. "Which code editor do you want to use?" - use the default value.
0. "What is your GitHub username?" - use whatever username you created in the Github account creation. 
0. "What is the name of the course's GitHub organization?" - this is `the-isf-academy`.
0. "What is the email address associated with your GitHub account?" - this should be your ISF student email.
0. "What name do you want to use in your git commits? " - this is your Github username.


> **When you are asked for your computer password, you won't see any letters appear as you type.** This is normal--it's to keep the person standing behind you from seeing your password.



{{< checkpoint >}}
Congratulations! You're finished! 

If you ran into any issues, please notify a teacher. 

{{</checkpoint >}}
