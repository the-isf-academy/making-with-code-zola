---
title: 6. Decomposition
type: labs
---

# Decomposition Lab

## A. Review of Modules

Today, we are going to analyze a repository made by a CS9 student from last year, Iris! Her project will be similar to what you will make for your upcoming Unit 0 project.

{{< code-action >}} To clone her repo, make sure you are in `unit_00` and then download it using git:

```shell
    TEA-JWOLF:unit_00 jwolf$ git clone https://github.com/the-isf-academy/unit_00_project_Iris.git
```

{{< look-action >}} There are quite a few modules being used here! Use `tree`, the `README.md` file, Atom, and the terminal to explore her project.

{{< checkpoint >}}
{{< write-action >}} Once you've fully explored her code, answer the following questions:

0. What terminal command do you use to run the non-animated version of her code?
1. What command do you use to run the animated version of her code?
2. Iris has four modules in her project. Name the modules here, and describe the purpose of each module in one sentence.
3. Iris has a variable called `sf`, which stands for size factor. You can change this variable in one file, and the size will get adjusted throughout the drawing. Which module would you edit in order to adjust the `sf` variable?

{{< /checkpoint >}}


## B. Intro to Decomposition

{{< include_resource "resource_decomposition" >}}

First, let's take a look at how Iris decomposed her still image. Then, we'll see how she decomposed the animation.

### Still Image

You may recognize who she drew! (Hover over the image to reveal)

<img src="/images/courses/cs9/unit00/00_decomp_winwin.png" style="width:100%"
  onmouseover="this.src='/images/courses/cs9/unit00/00_decomp_winwin2.jpg'; this.style.width = '100%';"
  onmouseout="this.src='/images/courses/cs9/unit00/00_decomp_winwin.png';"
/>

{{< checkpoint >}}
{{< look-action >}} Iris decided to tackle the project by drawing the figure and then the letters as still images. With your group, discuss the `figure.py`, `letters.py`, and `settings.py` modules.

{{< write-action >}} Answer the following questions in your Google Doc.

#### Figure.py
0. How many functions are in the module?
1. `draw_figure() ` is defined in `figure.py`, but where is `draw_figure() ` actually called in her project? (Hint: there are two files.)
2. Iris wrote an awesome `draw_figure()`function, but it is 190 lines long. Let's think about how we might decompose this code. If you could split `draw_figure()` into multiple smaller functions, what would those functions be? Explain in 2 - 3 sentences.

#### Letters.py
0. Why do you think Iris chose to create a separate module for letters? Explain in 1 sentence.
1. Where is `draw_W()` actually called in her project?

#### Settings
0. Many of Iris' functions accept a parameter called `sf`. `sf` stands for size factor. You can change this variable in one file, and the size will get adjusted throughout the drawing. Where is `sf` being defined?
1. Change `settings.SIZEFACTOR` to any number you like. How does this affect her still image when you run `no_animation.py`?
2. You might also have noticed that this module uses `fillcolor` to fill in shapes. You've seen `fill_color()` before,
but Iris uses a special code to determine the color of Win Win's shirt. Open the
[turtle documentation](https://docs.python.org/3.8/library/turtle.html?highlight=turtle#turtle.fillcolor) and read
about how filling works. Then, change the color of Win Win's shirt, and copy-paste the code into the Google Doc.


{{< /checkpoint >}}


## C. Animation

There are many ways to animate still images! Let's talk about these four:

{{< columns >}}
{{< figure src="images/courses/cs9/unit00/00_decomp_translate.gif" width="100%">}}
{{< figure src="images/courses/cs9/unit00/00_decomp_rotate.gif" width="100%">}}
<--->
{{< figure src="images/courses/cs9/unit00/00_decomp_scale.gif" width="100%">}}
{{< figure src="images/courses/cs9/unit00/00_decomp_frame.gif" width="100%">}}
{{< /columns >}}

{{< look-action >}} After Iris finishes drawing the still images, she uses one of the above strategies to animate her letters. With your group, discuss the files within the `animation.py` module.

{{< checkpoint >}}
{{< write-action >}} Answer the following questions in your Google Doc.

#### main() function
0. There is a for-loop in `main()` which repeats for `settings.NUMREPEATS` number of times. Go to `settings.NUMREPEATS` and change the number for the variable `NUMREPEATS`. Then run the code by using `python animation.py`. What does the for-loop do?

#### draw_stationary() function
0. Part of her project is being drawn in `draw_stationary()` and part of her project is being drawn in `draw_animation()`. Which parts of her drawing are being drawn in `draw_stationary()`?

#### draw_animation() function
0. The other part of her project is being drawn in `draw_animation()`. The for-loop in `draw_animation()` is responsible for the animation! You can think of an animation as a series of frames that are being flipped through very quickly. Based on the for-loop, how many frames are there in our animation?
1. Now let's check out the if-statements. This is called frame-based animation; the animations appear based on the frame number. What happens at the 10th frame? What happens at the 50th frame?
2. Change lines 20, 22, 24, 26, 28, and 30 so that the if-statements are set to different numbers. Try `i = 10` (for line 20), `i = 12` (for line 22), `i = 14` (for line 24), `i = 16` (for line 26), `i = 18` (for line 28), and `i = 20` (for line 30). What happens? Describe in 1 sentence.
3. Comment out line 32 `screen.update()`. Then run the code by using `python animation.py`. What happens?
Describe what happened and why you think it happened in 2 sentences.

{{< /checkpoint >}}

## D. More Animations

Here's an animation based on the unit project made by another CS9 student from last year, Jethro!

{{< look-action >}} Notice how the cat's face is stationary while the cat's arm is animated (using a rotation).


{{< figure src="images/courses/cs9/unit00/00_decomp_jethro.webp" width="100%">}}


{{< code-action >}} Now, we're going to explore each type of animation by looking at some small mystery examples. Make sure you are in `unit_00` and then download it using git:

```shell
    TEA-JWOLF:unit_00 jwolf$ git clone https://github.com/the-isf-academy/lab-decomposition.git
```

{{< checkpoint >}}

{{< write-action >}} Now answer the following questions with your team. You will be asked to change parts of the code!

### Animation Mystery 1
<!---frame-based -->
{{< code-action >}} Run the command `python animate_1.py` in terminal and then discuss the following:

0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. Look inside the `main()` function. How many times is the for-loop running, and how did you find this number?
2. Notice on line 21 that there's a timer set for `sleeptime` seconds that is being repeated for `num_frame` times. Calculate how long the animation lasts, using these two variables.
3. Frames Per Second (FPS) is a rate we care about in the field of animation. You can calculate this rate by dividing the total number of frames over the total length of the animation. Calculate the FPS of this animation.
4. Look inside the `draw_animation()` function. How many times is the for-loop here running, and how did you find this number? What is the difference between `settings.NUMREPEATS` and `settings.NUMFRAMES`?
5. You will see that there are four conditionals inside the for-loop of `draw_animation()`. Calculate what the numbers in the conditionals are equivalent to: `num_frames/4`, `num_frames/2`, `3*num_frames/4`, `num_frames`.
6. There are four if-statements, but only three triangles drawn on the screen. What happened to the fourth triangle? Explain in at least once sentence.
7. Change the last if-statement so that the animation is able to draw and animate all four triangles.

### Animation Mystery 2
<!---scale-->
{{< code-action >}} Run the command `python animate_2.py` in terminal and then discuss the following:

0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. Let's change some settings! Currently, the circle does not fit on the screen when it gets animated. Go to the `settings.py` file and change `START_X` and/or `START_Y` so that the animated circle is able to fit. While you're at it, let's also change `COLOR`.
2. You'll notice that we used two for-loops in this example. For the first for-loop, trace through the code and fill out the table for every `i` and `new_size`. (HINT: you can split up the work on this with your tablemates.)
3. Calculate `max_size`. (HINT: you will need to reference the numbers in `settings.py`)
4. For the second for-loop, trace through the code and fill out the table for every `j` and `new_size`.(HINT: you can split up the work on this with your tablemates.)
5. Change the code so that the animation only grows half as big (aka the `max_size` is half as large). (HINT: you only need to change something in `settings.py`)


### Animation Mystery 3
<!---translate-->
{{< code-action >}} Run the command `python animate_3.py` in terminal and then discuss the following:

0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. What does the `clear()` function do in line 18? What happens if you remove `clear()`?
2. Change the code so that the animation moves five times as far. (HINT: you will need to change two lines of code in `draw_animation()`)
3. What if you wanted to draw an animating square instead of a triangle? Write a new helper function in `parts.py` called `draw_square()` that takes two parameters: `side_len` and `color_name`. Then change line 15 in `animate_3.py` to `draw_square(side_len, color_name)`.

### Animation Mystery 4
<!---rotate-->
{{< code-action >}} Run the command `python animate_4.py` in terminal and then discuss the following:

0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. This animation involves three if-conditional branches, and each branch causes a different speed! Why is the second branch faster than the first
branch? Why is the third branch faster than the second branch?
2. Change the code so that the animation turns in the opposite direction for all three conditional branches. Describe in one sentence which lines of code you changed and how you changed the code.

{{< /checkpoint >}}


## Deliverables

- Each student should submit a Google Doc with answers to the questions above.
