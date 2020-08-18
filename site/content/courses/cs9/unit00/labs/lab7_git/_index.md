---
title: 7. Version Control
type: labs
draft: true
resources:
- name: GitHub
  src: images/courses/cs9/unit00/00_git_github.png

---
# Version Control Lab

{{< devnote >}}
fix "first day of class" link, replace links to isf repo
{{< /devnote >}}

## Set up

- Double-check that git is installed by running `which git` in Terminal.
  (We installed git on the [first day of class](lessons/lesson_00_00.md).)
  You should see the path where git is installed. If you see nothing, check with
  a teacher.
- Configure git: Type each of these commands into Terminal.
    - `git config --global user.name <Your name>`
    - `git config --global user.email <Your school email>`
    - `git config --global core.editor "atom --wait"`
    - `git config --global commit.template .commit_template`

## Your first repo

You have already cloned a few git repositories (remember typing `git clone
...`?) Cloning means pulling a copy of a repository down from github onto your
own computer. Now we are going to take the next step, forking a repository
(making your own copy) and adding to it.

From now on, your homework, labs, and projects will be provided as git repositories. We are going to start now, by setting up your final project for this unit.

### Join github

Start by making a github account for yourself.

- Go to [github.com](https://github.com).
- Enter a username, email address, and password.
    - Your username should not include your real name.
    - Please use your school email account.
    - Write your password down somewhere!
- You should get a verification email. Click the link to prove it's your email
  address.

### Creating your fork

Your teachers have already created a repository for the unit project. Each
student is going to fork this repository, so they have their own copy.

- [If you are in CS1, click this link](https://classroom.github.com/a/KrNLldo1)
- [If you are in CS2, click this link](https://classroom.github.com/a/SVz6RdzM)

Follow the instructions. Once your fork is created, you will get a link to your
project. Click it and you should see a screen like the one below.

{{< figure src="images/courses/cs9/unit00/00_git_github.png" width="400px" title="GitHub" >}}

### Cloning your fork

Now you are going to clone your repo, so there's a copy on your computer. If you
look at the following commands, you'll see that the `git clone` command has a
`******`. You need to replace this with your repo's URL, which you can get by
clicking on the green "Clone or download" button.

```shell
    cd ~/Documents/cs9/unit_0/
    git clone ******
```

Now you have a directory called `~/Documents/cs9/unit_0/unit-0-drawing-yourname`. Let's go into the project folder and have a look inside:

```shell
    cd unit-0-drawing-yourname
    tree .
```

There are just a few files in the project right now. You can also see the
history of changes to this repository, from before you forked it.

```shell
    git log
```

Press `esc` to leave the git log viewer.

**Stop. Check in with your group, and make sure everyone has completed the
steps above. Once your whole group is ready, raise your hand to check in with a
teacher.**

# Working with Git

Whenever you are working on a project, you will go through four steps:

- **Edit files**: Work on all the files in this project just like normal.
- **Review changes**: Look at your changes and make sure you are happy with
  them.
- **Commit**: Save your changes to the repository.
- **Push**: Push your copy of the repository up to github.

Let's practice.

## Step 0: Edit files

Today we are going to start working on the project plan, using the file
`planning.md`. Open it using Atom:

```shell
    atom planning.md
```

There are three sections here: the idea, decomposition, and milestone. Each
section has some text explaining what's expected. You should replace this text
with your actual project plan.

You don't have to write your whole project plan right now, but you need to make
some changes to practice using git. Under the first section, called "the idea",
write a short paragraph describing your idea for the final project. If you have
a bunch of different possible ideas, you can list them like this:

```shell
    - I was thinking I might draw a detailed self-portrait of my face.
    - I also thought it might be neat to make a drawing I can use to laser cut a
      customized rack for my desk at home. It will have holes just the right
      size for all my favorite pens and pencils.
    - I like to make T-shirts by cutting out stencils and spray-painting them. I
      want to draw some shapes I can use to laser-cut templates.
    - I want to draw the Hong Kong skyline.
```

By the way, this file is written in a simple language called Markdown that
allows you to format text. [Here's a quick guide to
markdown](https://www.markdownguide.org/cheat-sheet). When you have a `.md` file
open in Atom, you can preview the rendered version with the following menu
option: `Packages > Markdown Preview > Toggle Preview`.

## Step 1: Review changes

Once you have made some changes to `planning.md`, save your work in Atom and go
back to the Terminal. Let's use git to see what changes you have made. Type:

```shell
    git status
```shell

You will see the following message:

```shell
    On branch master
    Your branch is up to date with 'origin/master'.

    Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git checkout -- <file>..." to discard changes in working directory)

	    modified:   planning.md

    no changes added to commit (use "git add" and/or "git commit -a")
```

Read the whole message. It is telling you that only file that you
have changed is `planning.md`. Yup. But what changes did you make? Let's use
another command to get some more detail:

```shell
    git diff
```

Now you will see a description of what you have added and what you have removed
from `planning.md`:

```shell
    diff --git a/planning.md b/planning.md
    index ac006b3..90b0e4f 100644
    --- a/planning.md
    +++ b/planning.md
    @@ -2,10 +2,13 @@

    ## The idea

    -Replace this text with a description of the drawing you want to make. (It would be nice to also explain why you want to make this drawing.) It's helpful, but not required, to include a sketch of what you are planning. If you want to add an image, you can do so like this:
    -
    -![A description of the image, in case the person reading is blind](images/sample.jpg)
    -
    +- I was thinking I might draw a detailed semf-portrait of my face.
    +- I also thought it might be neat to make a drawing I can use to laser cut a
    +  customized rack for my desk at home. It will have holes just the right
    +  size for all my favorite pens and pencils.
    +- I like to make T-shirts by cutting out stencils and spray-painting them. I
    +  want to draw some shapes I can use to laser-cut templates.
    +- I want to draw the Hong Kong skyline.

    ## Decomposition
```

You should always run `git status` and `git diff` before you add changes to your
repository, to make sure you're saving the changes you meant to add. If you
noticed any typos, or want to add something, edit `planning.md` in Atom again,
and then run `git status` and `git diff` again.

## Step 2: Commit

Now it's time to add these changes to your repository. A *commit* is a
collection of one or more changes that belong together. For example, if you
wanted to add a photo of a sketch to your planning document, you would need to
edit `planning.md`, telling it to include the photo. You would also need to add
the image file itself to the repo. These two changes belong together, so they
should be part of the same commit.

You will prepare a commit by adding all the files that have changes. Right now,
it's just `planning.md`, so let's add it to a new commit:

```shell
    git add planning.md
```

Run `git status` again, and you will see that `planning.md` has gone from red to
green because it has been added to a new commit.

```shell
    On branch master
    Your branch is up to date with 'origin/master'.

    Changes to be committed:
    (use "git reset HEAD <file>..." to unstage)

	    modified:   planning.md
```

Now we are ready to finalize the commit. Type `git commit` and you will see an
Atom file open. It's time to describe what you did, using a commit message.

Every time you commit code, you need to write a message explaining what you have done. Anybody reading your code (teachers, peers, a future version of you) will read the log of your changes to understand what has been happening on the project. The file that opens contains a template explaining how to write your commit message.

Once you finish, save the file and close it. Run `git log` to see the history of
your project. You should see your commit right at the top. Congratulations!

## Step 3: Push

Now it's time to sync the copy of your repo with the copy on github. Type `git
push`. Reload your repository page on Github (remember the green button?). Click
on `planning.md`; you should see your updated version.

This probably felt like a lot of work just to save your work. That's true. But
it will get easier as you get used to it, and you will start to see the value of
using git when you start working on bigger projects. If you're not glad you
learned git five years from now, come see us and we'll give you some extra
credit or something :)

**Check in with your table group and make sure everyone succeeds in committing a
change. Once everyone has succeeded, check in with a teacher.**

## Deliverables
There is no file to turn in for this lab. Instead, you are expected to complete
the instructions in this lab, so that your teachers can see your final project
repository with a new commit message from you.
