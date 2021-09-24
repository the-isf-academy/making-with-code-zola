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

### [Command Line]

{{< code-action "Double-check that git is installed" >}}  by running `which git` in Terminal.

> You should see the path where git is installed. If you see nothing, check with a teacher.

{{< code-action "Configure git">}} : Type each of these commands into Terminal. 

> Make sure to replace the information inside the `< >` with your information.

- `git config --global user.name <Your name>`
- `git config --global user.email <Your school email>`
- `git config --global core.editor "atom --wait"`
- `git config --global commit.template .commit_template`

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

{{< code-action "Go to your github settings:">}}  [github.com/settings/profile](https://github.com/settings/profile).

> 0. **Select** `Developer settings` from the sidebar.
> 0. **Select** `Personal access tokens`.
> 0. **Select** `Generate new token`.
> 0. **Type** `CS9` in the `Note` box.
> 0. **Set** the `Expiration` to `90 days`.
> 0. **Check** the `repo` box.
> 0. **Select** `Generate token` at the bottom of the page. 

{{< code-action "Copy your token to your Notes application.">}} 


## [1] Your First Repo

**From now on, your homework, labs, and projects will be provided as git repositories.** We are going to start now, by setting up your final project for this unit.


### [Cloning Your Project Repository]

{{< code-action "Clone your repo, so there's a copy on your computer." >}}  

> Below you'll see that the `git clone` command has a `YOUR-GITHUB-USERNAME`. 
>
> **You need to replace this with your username**
>
> e.g. git clone project-animation-emmaqbrown


```shell
cd ~/Desktop/cs9/unit_00/
git clone project-animation-YOUR-GITHUB-USERNAME
```

If successful, should see something like this in your Terminal:
```shell
Cloning into 'project-animation-YOUR-GITHUB-USERNAME'...
remote: Enumerating objects: 33, done.
remote: Counting objects: 100% (33/33), done.
remote: Compressing objects: 100% (22/22), done.
remote: Total 33 (delta 13), reused 22 (delta 8), pack-reused 0
Receiving objects: 100% (33/33), 7.51 KiB | 7.51 MiB/s, done.
Resolving deltas: 100% (13/13), done.
```

Now you have a directory called `project-animation-YOUR-GITHUB-USERNAME` in your `cs9/unit_00` folder. 

{{< code-action "Let's go into the project folder and have a look inside:" >}} 

```shell
cd project-animation-YOUR-GITHUB-USERNAME
tree .
```

There are just a few files in the project right now. 


# Working with Git

Whenever you are working on a project, you will go through four steps:

- **Edit files**: Work on all the files in this project just like normal.
- **Review changes**: Look at your changes and make sure you are happy with
  them.
- **Commit**: Save your changes to the repository.
- **Push**: Push your copy of the repository up to github.

Let's practice.

### [Step 0: Edit files]

Today we are going to start working on the project, starting with the design. 

{{< code-action "Open the" >}}  `README.md` **file using Atom:**

```shell
atom README.md
```

As you've seen before, `README` files are like a guide to what's contained inside
a repository and how to use it. Once your project is complete, your `README` file
will serve this purpose.

There are four sections here: Planning, How to use, Settings, and Modules. Each
section has some text explaining what's expected. You should replace this text
with descriptions of your project.


To get started, you will link your design document into your `README.md` file.

{{< code-action "Find your project design document in your Google Drive and link in your" >}} `README.md`.

> Use the follow syntax to create a hyperlink:
> 
> `[9. Version Control](www.cs.fablearn.org)`
>
> This will result in: [9. Version Control](www.cs.fablearn.org)

{{< aside "Markdown" >}}
The `README.md` file is written in a simple language called Markdown that
allows you to format text. 

[Here's a quick guide to
markdown](https://www.markdownguide.org/cheat-sheet). 

When you have a `.md` file
open in Atom, you can preview the rendered version with the following menu
option: `Packages > Markdown Preview > Toggle Preview`.
{{< /aside >}}

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
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

    modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

**Read the whole message.** 

It is telling you that only file that you have changed is `README.md`. That's correct, but what changes did you make? 

{{< code-action "Let's use another command to get details about what changes were made:" >}}

```shell
git diff
```

Now you will see a description of what you have added and what you have removed
from `README.md`:

```shell
diff --git a/README.md b/README.md
index 0d8c5de..d0eeb94 100644
--- a/README.md
+++ b/README.md
@@ -12,7 +12,7 @@ Here's what is included:
 - `settings.py` This is where you will store your settings for your animation. Feel free to add more settings to further parameterize your project. 
 
 ## Planning
-<Insert a link to your planning document here.>
+[Here is a link to my planning document](www.url.com)
 
 ## How to use
 <Describe how to run your animation here.>
```

You should always run `git status` and `git diff` before you add changes to your
repository, to make sure you're saving the changes you meant to add. 

If you noticed any typos, or want to add something, edit `README.md` in Atom again, and then run `git status` and `git diff` again.

---

### [Step 2: Commit]

Now it's time to add these changes to your repository. 

**A *commit* is a collection of one or more changes that belong together.** 

For example, if you wanted to add a photo of a sketch to your README document, you would need to 

0. edit `README.md`, telling it to include the photo
0. add the image file itself to the repo. 

These two changes belong together, so they should be part of the same commit.

**You will prepare a commit by adding all the files that have changes.**

{{< code-action "Let's add your" >}} `README.md` to a new commit:

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

{{< code-action "Type" >}} `git commit`.  You will see an
Atom file open. 

**It's time to describe what you did, using a commit message.**

Every time you commit code, you need to write a message explaining what you have done. Anybody reading your code (teachers, peers, a future version of you) will read the  log of your changes to understand what has been happening on the project. 

{{< code-action "Follow the template and write your commit message." >}} Once you finish, save and close it.

{{< code-action "Run" >}} `git log` to see the history of your project. You should see your commit right at the top. 

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
To https://github.com/the-isf-academy/unit_00_project_Iris.git
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


