---
title: 6. Decomposition
type: labs
---

# Decomposition Lab

## A. Review of Modules

Today, we are going to analyze a repository made by a CS9 student from last year, Iris! Her project will be similar to what you will make for your upcoming Unit 0 project.

To clone her repo, make sure you are in `unit_00` and then download it using git:

```shell
    TEA-JWOLF:unit_00 jwolf$ git clone https://github.com/the-isf-academy/unit_00_project_Iris.git
```

There are quite a few modules being used here! Use `tree`, the `READ.ME`, Atom, and the terminal to explore her project.

{{< checkpoint >}}
Once you've fully explored her code, answer the following questions:

0. What command in the terminal do you use to run the still version of her code?
1. What command do you use to run the animated version of her code?
2. Iris has four modules in her project. Name the modules, and describe the purpose of each module in the table.

{{< /checkpoint >}}


## B. Intro to Decomposition

{{< include_resource "resource_decomposition" >}}

First, let's take a look at how Iris decomposed her still image. Then, we'll see how she decomposed the animation.

### Still Image

You may recognize who she drew! (Hover over the image to reveal)

<img src="https://i.ibb.co/88HvLn9/winwin-cs9.png" style="width:100%"
  onmouseover="this.src='https://i.ibb.co/hRWS317/winwin.jpg'; this.style.width = '100%';"
  onmouseout="this.src='https://i.ibb.co/88HvLn9/winwin-cs9.png';"
/>


{{< checkpoint >}}
Iris decided to tackle the project by drawing the figure and then the letters as still images. With your group, discuss the `figure.py`, `letters.py`, and `settings.py` modules. Answer the following questions in your Google Doc.

#### Figures
0. How many functions are in the module?
1. Where is `draw_figure() ` actually used in her project?
2. Iris wrote an awesome `draw_figure()`function, but it is 190 lines long. Let's think about how we might decompose this code. If you could split `draw_figure()` into multiple smaller functions, what would those functions be? Explain in 2 - 3 sentences.

#### Letters
0. Why do you think Iris chose to create a separate module for letters? Explain in 1 sentence.
1. Where is `draw_W() ` actually called in her project?

#### Settings
0. Many of Iris' functions accept a parameter called `settings.sf`. `sf` stands for size factor. You can change this variable in one file, and the size will get adjusted throughout the drawing. Where is `sf` being defined?
1. Change `settings.sf` to any number you like. How does this affect her still image when you run `no_animation.py`?
2. You might also have noticed that this module uses `fillcolor` to fill in shapes. You could open the [turtle documentation](https://docs.python.org/3.7/library/turtle.html?highlight=turtle#turtle.fillcolor) and read about how filling works. Change the color of Win Win's shirt, and copy-paste the code into the Google Doc.


{{< /checkpoint >}}


### Animation

There are many ways to animate still images! Let's talk about these four:

<p float="left">
  <img src="https://media.giphy.com/media/W5yFa0XnoKMJcuJ7fB/giphy.gif" width="45%" />
  <img src="https://media.giphy.com/media/K2PvDFPTvU53UeGfqN/giphy.gif" width="45%" />
  <img src="https://media.giphy.com/media/wmbbW5bH6LgKWwo8tu/giphy.gif" width="45%" />
  <img src="https://media.giphy.com/media/7mKO90CephI5Z3ysQg/giphy.gif" width="45%" />
</p>

{{< checkpoint >}}
After Iris finishes drawing the still images, she uses one of the above strategies to animate her letters. With your group, discuss the files within the `animation.py` module. Answer the following questions in your Google Doc.

#### main() function
0. There is a for-loop in `main()` which repeats for `loop_num` number of times. Go to `settings.loop_num` and change the number for the variable `loop_num`. Then run the code by using `python animation.py`. What does the for-loop do?

#### draw_stationary() function
0. Part of her project is being drawn in `draw_stationary()` and part of her project is being drawn in `draw_animation()`. Which parts of her drawing are being drawn in `draw_stationary()`?

#### draw_animation() function
0. The other part of her project is being drawn in `draw_animation()`. The for-loop in `draw_animation()` is responsible for the animation! You can think of an animation as a series of frames that are being flipped through very quickly. Based on the for-loop, how many frames are there in our animation (hint: check the range)?
1. Now let's check out the if-statements. This is called frame-based animation; the animations appear based on the frame number. What happens at the 10th frame? What happens at the 50th frame?
2. Change lines 32, 34, 36, 38, 40, and 42 so that the if-statements are set to different numbers. Try `i = 10` (for line 32), `i = 12` (for line 34), `i = 14` (for line 36), `i = 16` (for line 38), `i = 18` (for line 40), and `i = 20` (for line 42). What happens? Describe in 1 sentence.
3. Comment out line 44 `screen.update()` and line 45 `time.sleep(0.05)`. Then run the code by using `python animation.py`. What happens? Describe in 1 sentence. 

{{< /checkpoint >}}

## C. More Animations

Now, we are going to examine a unit project made by another CS9 student from last year, Jethro!


<img src="https://media.giphy.com/media/wNUofiacijQ8mVnSvU/giphy.gif" style="width:100%"/>


Make sure you are in `unit_00` and then download it using git:

```shell
    TEA-JWOLF:unit_00 jwolf$ git clone https://github.com/the-isf-academy/unit-0-drawing-yobamos912
```

{{< checkpoint >}}

Now answer the following questions with your team. You will be asked to change parts of Jethro's code!

### Animation Set Up
0. What does the for-loop in  `main()` do? Explain in 1 sentence.
1. How is `draw_stationary()` different from the code in `no_animation.py`? Explain in 1 sentence.
2. What does `s.whisker_len` do? Where is it being defined? Explain in 1 sentence.

### Animation Mystery 1
<!-- - rotation -->
In animation.py, change `line 68` to `animate_v1()`. Run the code in terminal and then discuss the following:

0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. Look inside the `animate_v1()` function. What does the first for-loop do? What does the second for-loop do?
2. Find a way to change the speed of the animation. Copy-paste your code here.

### Animation Mystery 2
<!-- - Scale -->
In animation.py, change `line 68` to `animate_v2()`. Run the code in terminal and then discuss the following:

0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. Look inside the `animate_v2()` function. What does the first for-loop do? What does the second for-loop do?
2. What does the `clear()` function do in line 51? What happens if you remove `clear()`?

### Animation Mystery 3
<!-- - translation (failed) -->
In animation.py, change `line 68` to `animate_v2()`. Run the code in terminal and then discuss the following:

0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. Why does the animation fail?
2. Find a way to fix the animation. Copy-paste your code here.

{{< /checkpoint >}}


## Deliverables

- Each student should submit a Google Doc with answers to the questions above.
