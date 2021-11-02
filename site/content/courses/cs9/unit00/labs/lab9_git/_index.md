---
title: 9. Version Control
type: labs
resources:
- name: GitHub
  src: images/courses/cs9/unit00/00_git_github.png
# draft: true
---
# Version Control Lab

{{< devnote >}}
fix "first day of class" link, replace links to isf repo
{{< /devnote >}}

In this lab, we're going to learn two new tools, git and Github, to help us with version control.

## [0] Github Set up

You have already used git a few times. Rmember typing `git clone
...`? Cloning means pulling a copy of a repository down from github onto your
own computer. Now we are going to take the next step, editing a repository and pushing it to the cloud. 

First, we must set up your Terminal and create a Github account. 

### [Terminal]

{{< code-action "Double-check that git is installed" >}}  by running `which git` in Terminal.

> You should see the path where git is installed. If you see nothing, check with a teacher.

{{< code-action "Configure git">}} : Type each of these commands into Terminal. 

> Make sure to replace the information inside the `< >` with your information.

- `git config --global user.name <Your name>`
- `git config --global user.email <Your school email>`
- `git config --global core.editor "atom --wait"`
- `git config --global commit.template .commit_template`

{{< code-action "Install a credential manager to store your Github credentials securely." >}} *Copy and paste the lines below one at a time. It may ask you for your computer password.*
```shell
brew tap microsoft/git
brew install --cask git-credential-manager-core
```

### [Join Github]



**You should have recieved an email inviation to join the ISF GitHub organization. If you did not, let a teacher know.**

{{< code-action "Accept the email invitation to join the ISF Github organization">}} 

> - Click on the "Join @the-isf-academy" button in the email from GitHub
> - Enter a username, email address, and password.
>  - Your username should not include your real name.
>    - Please use your school email account.
>    - Write your password down somewhere!
> - You should get a verification email. Click the link to prove it's your email
>  address.

### [Get Github Token]

Github uses personal access tokens to ensure security when remotely accessing a repository. You will need your token when using git from the Terminal. 

{{< code-action "Go to your github settings:">}}  [https://github.com/settings/tokens](https://github.com/settings/tokens).

> 0. **Select** `Generate new token`.
> 0. **Type** `CS9` in the `Note` box.
> 0. **Set** the `Expiration` to `90 days`.
> 0. **Check** the `repo` box.
> 0. **Select** `Generate token` at the bottom of the page. 

{{< code-action "Copy your token to your Notes application.">}} 


## [1] Your First Repo

**From now on, your do nows labs, and projects will be stored as git repositories.** We are going to start now, by setting up your `do_now` files on Github. 


### [Cloning Your Do Now Repository]

We have set up repositories for each student to populate with their do now files.

{{< code-action "Go to your" >}} `cs9` **folder.**

```shell
cd Desktop/cs9
```

{{< code-action "Clone your repo. This will copy it onto your computer." >}}  

> Below you'll see that the `git clone` command has a `YOUR-GITHUB-USERNAME`. 
>
> **You need to replace this with your username**
>
> *e.g. `git clone cs9-donows-emmaqbrown`*


```shell
git clone cs9-donows-YOUR-GITHUB-USERNAME
```

If successful, should see something like this in your Terminal:
```shell
Cloning into 'cs9-donows-YOUR-GITHUB-USERNAME'...
remote: Enumerating objects: 33, done.
remote: Counting objects: 100% (33/33), done.
remote: Compressing objects: 100% (22/22), done.
remote: Total 33 (delta 13), reused 22 (delta 8), pack-reused 0
Receiving objects: 100% (33/33), 7.51 KiB | 7.51 MiB/s, done.
Resolving deltas: 100% (13/13), done.
```

Now you have a directory called `cs9-donows-YOUR-GITHUB-USERNAME` in your `cs9` folder. 

{{< code-action "Go into your folder and use the" >}} `tree .` **command to see the directory's file structure.** Right now there is only one file, `README.md`, and one folder, `unit_00`. 
```shell
.
├── README.md
└── unit_00
```

## [2] Working with Git

Whenever you are working on a project, you will go through four steps:

- **Edit files**: Work on all the files in this project just like normal.
- **Review changes**: Look at your changes and make sure you are happy with
  them.
- **Commit**: Save your changes to the repository.
- **Push**: Push your copy of the repository up to github.

Let's practice.

### [Step 0: Edit the README]

Today we are going to practice commiting files to Github. Let's start by editing the `README.md` file. 

{{< code-action "Open the" >}}  `README.md` **file using Atom:**

```shell
atom README.md
```

As you've seen before, `README` files are like a guide to what's contained inside
a repository and how to use it. 

Right now the `README` is pretty bare. 

{{< code-action "Update it with your name, description of what this repository will hold, and a link to the Do Now page on the website." >}}


{{< aside "Markdown" >}}
The `README.md` file is written in a simple language called Markdown that
allows you to format text. 

[Here's a quick guide to
markdown](https://www.markdownguide.org/cheat-sheet). 

When you have a `.md` file
open in Atom, you can preview the rendered version with the following menu
option: `Packages > Markdown Preview > Toggle Preview`.
{{< /aside >}}

Your final markdown file should look something like this:
```md
# Do Nows
### Author: Ms. Brown

This repository holds the do now exercises. The exercises can be found (here)[http://localhost:1313/courses/cs9/unit00/do_now/].
```

--- 

### [Step 1: Review changes]

Once you have made some changes to `README.md`, save your work in Atom and go
back to the Terminal. 

{{< code-action "Let's use git to see what changes you have made." >}}

```shell
git status
```

You will see the following message:

```shell
On branch master
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

    modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

👀 **Read the whole message.** It is telling you that only file that you have changed is `README.md`. That's correct, but what changes did you make? 

{{< code-action "Let's use another command to get details about what changes were made:" >}}

```shell
git diff
```

Now you will see a description of what you have added and what you have removed
from `README.md`:

```shell
diff --git a/README.md b/README.md
index 2c637ca..00ca290 100644
--- a/README.md
+++ b/README.md
@@ -1,9 +1,4 @@
 # Do Nows
-### Author: YOUR NAME GOES HERE
+### Author: Ms. Brown
 
-
-> INCLUDE THE FOLLOWING:
-> - A description of this repository
-> - A link to the `do now` page of the website.
->
-> *You may delete this section when complete.*
\ No newline at end of file
+This repository holds the do now exercises. The exercises can be found (here)[http://localhost:1313/courses/cs9/unit00/do_now/].
```

> To get out of `git diff`, type `q` then `return`.

**You should always run at a minimum run `git status` before you add changes to your repository.** To make sure you're adding the changes you meant to add, run  `git diff`. 

If you noticed any typos, or want to add something, edit `README.md` in Atom again, and then run `git status` and `git diff` again.

---

### [Step 2: Commit]

Now it's time to add these changes to your repository. 

**A *commit* is a collection of one or more changes that belong together.** 

For example, if you wanted to add a photo to your README document, you would need to 

0. edit `README.md`, telling it to include the photo
0. add the image file itself to the repo. 

These two changes belong together, so they should be part of the same commit.

**You will prepare a commit by adding all the files that have changes.**

{{< code-action "Let's add your" >}} `README.md` **to a new commit:**

```shell
git add README.md
```

{{< code-action "Run" >}} `git status` **again.** You will see that `README.md` has gone from red to green because it has been added to a new commit.

```shell
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
(use "git reset HEAD <file>..." to unstage)

    modified:   README.md
```

Now we are ready to finalize the commit. 

{{< code-action "Type" >}} `git commit`. **You will see an Atom file open.** If Atom does not open, notify a teacher.

**It's time to describe what you did, using a commit message.**

Every time you commit code, you need to write a message explaining what you have done. Anybody reading your code (teachers, peers, a future version of you) will read the  log of your changes to understand what has been happening on the project. 

{{< code-action "Follow the template and write your commit message." >}} Once you finish, save and close it.

{{< code-action "Run" >}} `git log` **to see the history of your project.** You should see your commit right at the top. 

---

### [Step 3: Push]

Now it's time to sync the copy of your repo with the copy on github.

{{< code-action "Type" >}}  `git push`. 
> It may ask you for your username. **This is the `Github` username you just created.**
>
> It may ask you for your password. **This is your Github `token` you copied in the setup.**
>
> Your token will NOT appear when you copy and paste it.

You should see something below in Terminal. If you do not, tell a teacher.
```shell
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 302 bytes | 302.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/the-isf-academy/cs9-donows-YOUR-GITHUB-USERNAME
   67838f1..4742ecf  main -> main
```

{{< code-action "Go to yoour repository page on Github.com." >}} You should see your updated version of your `README.md` at the bottom of the page.

**🎉 Congratulations! You have successfully made your fist push to Github! 🎉**

This probably felt like a lot of work just to save your work. That's true. But
it will get easier as you get used to it, and you will start to see the value of
using git when you start working on bigger projects. 

*If you're not glad you
learned git five years from now, come see us and we'll give you some extra
credit or something :)*

## [2] Adding your preious Do Nows

We are now going to add all of your previous `Do Nows` to your repository. 

{{< code-action "Open your finder, and drag all of your Do Now files into your repository." >}} 

{{< code-action "Then, navigate back to your repository in Terminal and make sure your files are in the correct place." >}} Your repository should look something like this:
```shell
tree .
.
├── README.md
├── unit_00
        ├── do_now_1.py
        ├── do_now_2.py
        ├── do_now_3.py
        ├── do_now_4.py
        ├── do_now_5.py
        ├── do_now_6.py
```

{{< code-action "Check what has changed in the repository with" >}} `git status`

{{< code-action "Add all of your do now files to the commit." >}} 
> You can add multiple files by separating file names with a `space` like so:
>
> `git add do_now_1.py do_now_2.py`

{{< code-action "Check the files have all been successfully added with" >}} `git status` 

{{< code-action "Finalize the commit by writing the commit message with" >}} `git commit`

{{< code-action "Push your commit to the remote copy of the repository with" >}} `git push`

{{< code-action "Finally, check your repository on Github.com!" >}} You should see all of your do now files listed. 



{{< checkpoint >}}
In your notebook, answer the following prompts.

0. How do you review your changes in a git repository?
0. How do you commit your changes in a git repository?
0. What is the purpose of a commit message?
0. How do you sync your local copy of the git repository to the remote copy on github.com? 
{{< /checkpoint >}}

---

# [2] Github Commands

| Command          | What it does                               |
|------------------|--------------------------------------------|
| `git status`     | displays the state of the repo             |
| `git add <file>` | adds a file to the commit                  |
| `git commit`     | records changes to the repo                |
| `git push`       | updates remote repo with your local repo   |
| `git diff`       | displays list of changes since last commit |
| `git log`        | displays list of most recent commits       |


