---
title: "Terminal Practice Homework"
type: module
---

# Terminal Practice Homework

## Part 0 (20 minutes)

Create your own Terminal Adventure game with directories and text files. Start by navigating to your Unit 00 directory and creating a new directory to hold your adventure. This directory should be called `homework_02`:

```shell
    ~$ cd Desktop/cs9/unit_00/
    ~/Desktop/cs9/unit_00$ mkdir homework_02
    ~/Desktop/cs9/unit_00$ cd homework_02
```

Now you can create directories (using `mkdir moon_base`) and you can add text files (using `atom space_station.txt`). Your adventure should have at least three directories and three text files; you may add as many as you want. (The Terminal commands you learned during the {{< ref_module "lab_terminal_adventure" >}} might be useful.)

### How to turn in your adventure
When you finish, you will turn your adventure in to Moodle. First, though, we need to zip up all these directories and files into a single file. We'll use a program called `tar` to do this. (`tar` stands for "tape archive" because it was originally used to create backups to be stored on magnetip tape!) Make sure you are in the `unit_00` directory.

```shell
    ~/Desktop/cs9/unit_00$ ls
    homework_01.py	homework_02
    ~/Desktop/cs9/unit_00$ tar -czf homework_02.zip homework_02
    ~/Desktop/cs9/unit_00$ ls
    homework_01.py	homework_02	homework_02.zip
```

Now you can turn in `homework_02.zip`, and your teachers will be able to unzip it to play your adventure.


## Part 1 (10 minutes)
*This part should take about 10 minutes*

Teach somebody else how to play your Terminal Adventure game. This could be a parent, grandparent, sibling, or friend--anyone you want.

You will have to write a short reflection during class about your experience teaching as a computer scientist.

## Deliverables
- A zip file containing at least three directories and at least three text files.
- A player should experience some kind of game or story when navigating these directories and text files.
