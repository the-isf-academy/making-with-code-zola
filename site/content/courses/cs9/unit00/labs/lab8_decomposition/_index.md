---
title: 8. Decomposition
type: labs
# draft: true
---

# Decomposition Lab

In this lab we are going to explore a key computer science concept, decomposition.


## [0] What is Decomposition?

Decomposition is the act of breaking down a problem into smaller, more manageable parts. This is an incredibly useful problem solving technique, even outside of computer science.

For example, let's consider the problem of baking a birthday cake. We can break this down into large overarching pieces such as the cake, the icing, and the assembly. Then each of those pieces can be broken down even further until you get to each individual ingredient.
- cake  
  - mixing the batter
    - dry ingredients
    - wet ingredients
  - baking the batter
    - temperture
    - time
  - cooling the cake
- icing
  - mixing the icing
    - flavor
    - color
- assemble the cake
  - frost the cake
  - add sprinkles

When thinking about complex problems there are two ways to approach them: top-down and bottom-up. Some people like to start with top-down thinking; others prefer bottom-up. Usually we need to use both.

- Top down means thinking about the problem as a whole, and how it could be broken up into a few smaller pieces. Then each of those smaller pieces could be broken into even smaller pieces.

- Bottom-up means starting with tiny chunks that are so simple we can already solve them, and using them to build gradually larger pieces, until you've solved the problem.

For example, let's consider baking again.
- Top-down: You need to make a birthday cake, and so you figure out the steps and the ingredients.  
- Bottom-up: You take a look at your all of your baking supplies and ingredients at home, and figure out you can make a birthday cake.




---
## [1] Iris's Project

Today, we are going to analyze a repository made by a previous CS9 student, Iris! Pay special attention to how she decomposed her idea into parts. Her project will be similar to what you will make for your upcoming Unit 00 project.

{{< code-action "Start by creating a " >}} `lab_08_decomposition` **folder.**

``` shell
cd Desktop/cs9/unit_00
mkdir lab_08_decomposition
```

{{< code-action "Using git, clone her repository inside your " >}} `lab_08_decomposition` folder.

```shell
cd lab_08_decomposition
git clone https://github.com/the-isf-academy/unit_00_project_Iris.git
cd unit_00_project_Iris
```

{{< look-action >}} **There are quite a few modules being used here! Use `tree` command to take a look.**

```shell
tree .
.
├── README.md
├── animation.py
├── figure.py
├── helpers.py
├── letters.py
├── no_animation.py
└── settings.py
```
<br>

### [Still Image]

First, let's take a look at how Iris decomposed her still image. Then, we'll see how she decomposed the animation.

{{< code-action "Start by running her still image file." >}}
```shell
python3 no_animation.py
```


You may recognize who she drew! (Hover over the image to reveal)

<img src="/images/courses/cs9/unit00/00_decomp_winwin.png" style="width:65%"
  onmouseover="this.src='/images/courses/cs9/unit00/00_decomp_winwin2.jpg'; this.style.width = '50%';"
  onmouseout="this.src='/images/courses/cs9/unit00/00_decomp_winwin.png';"
/>

Iris decided to tackle the project by drawing the figure and then the letters as still images. With your group, discuss the `figure.py`, `letters.py`, and `settings.py` modules.

{{< code-action "Open the repository in atom so you can easily examine in module." >}}
```shell
atom .
```


{{< checkpoint >}}


{{< write-action "Answer the following questions with your group." >}}

#### `figure.py`
0. How many functions are in the `figure.py` module? What are they and what do they do?
1. `draw_figure()` is defined in `figure.py`, but where is `draw_figure()` actually called in her project? (Hint: there are two files.)
2. Iris wrote an awesome `draw_figure()` function, but it is 190 lines long. Let's think about how we might decompose this code. If you could split `draw_figure()` into multiple smaller functions, what would those functions be? Explain in 2 - 3 sentences.

#### `letters.py`
0. How many functions are in the `letters.py` module? What are they and what do they do?
0. Why do you think Iris chose to create a separate module for letters? Explain in 1 sentence.
0. Where is `letter_w()` actually called in her project?

#### `settings.py`
0. How does changing the `SIZEFACTOR` variable change the drawing of `no_animation.py`?
0. How does changing the `START_X` variable change the drawing of `no_animation.py`?
0. How does changing the `START_Y` variable change the drawing of `no_animation.py`?
0. How does changing the `SHIRT_COLOR` variable change the drawing of `no_animation.py`?
{{< /checkpoint >}}


### [Animation]

Now that we understand how she created the still image, let's take a look at how she animated the letters.

{{< code-action "Run her animation file." >}}
```shell
python3 animation.py
```

{{< figure src="images/courses/cs9/unit00/00_decomp_winwin3.gif" width="75%">}}




{{< checkpoint >}}

{{< write-action "Answer the following questions with your group." >}}

#### `main()` in `animation.py`
0. There is a for-loop in `main()` which repeats for `settings.NUMREPEATS` number of times. Find where that varaible is set and change its value. What changed and what does the for-loop do?

#### `draw_stationary()` in `animation.py`
0. What is being drawn in `draw_stationary()`?

#### `draw_animation()` in `animation.py`
0. What is being drawn in `draw_animation()`?
0. The for-loop in `draw_animation()` is responsible for the animation! You can think of an animation as a series of frames that are being flipped through very quickly. Based on the for-loop, how many frames are there in our animation?
1. Now let's check out the if-statements. This is called frame-based animation; the animations appear based on the frame number. What happens at the 10th frame? What happens at the 50th frame?
2. Change lines 18, 20, 22, 24, 26, and 28 so that the if-statements are set to different numbers. Try `i == 10` (for line 20), `i == 12` (for line 22), `i == 14` (for line 24), `i == 16` (for line 26), `i == 18` (for line 28), and `i == 20` (for line 30). What happens? Describe in 1 sentence.
3. Comment out line 32 `screen.update()`. Then run the code by using `python animation.py`. What happens?
Describe what happened and why you think it happened in 2 sentences.

{{< /checkpoint >}}

<hr>

## [2] More Animations

There are many ways to animate still images! Let's talk about these four:

{{< columns >}}
{{< figure src="images/courses/cs9/unit00/00_decomp_translate.gif" width="100%">}}
{{< figure src="images/courses/cs9/unit00/00_decomp_rotate.gif" width="100%">}}
<--->
{{< figure src="images/courses/cs9/unit00/00_decomp_scale.gif" width="100%">}}
{{< figure src="images/courses/cs9/unit00/00_decomp_frame.gif" width="100%">}}
{{< /columns >}}

We're going to explore each type of animation by looking at some small mystery examples.

{{< code-action "Using git, download the repository with the mystery examples into your" >}} `lab_08_decomposition` folder.

```shell
git clone https://github.com/the-isf-academy/lab-decomposition.git
```


{{< code-action >}}{{< write-action >}} **Throughout this section, you will be asked to change part of the code and answer checkpoint questions about the following files:**
- `animate_1.py`
- `animate_2.py`
- `animate_3.py`
- `animate_4.py`

### [Animation Mystery 1]

{{< code-action "Run the" >}} `animate_1.py` **file.**

{{< checkpoint >}}

{{< write-action "Answer the following questions with your group." >}}


0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. Look inside the `main()` function. How many times is the for-loop running, and how did you find this number?
2. Notice on line 21 that there's a timer set for `sleeptime` seconds that is being repeated for `num_frame` times. Calculate how long the animation lasts, using these two variables.
3. Frames Per Second (FPS) is a rate we care about in the field of animation. You can calculate this rate by dividing the total number of frames over the total length of the animation. Calculate the FPS of this animation.
4. Look inside the `draw_animation()` function. How many times is the for-loop here running, and how did you find this number? What is the difference between `settings.NUMREPEATS` and `settings.NUMFRAMES`?
5. You will see that there are four conditionals inside the for-loop of `draw_animation()`. Calculate what the numbers in the conditionals are equivalent to: `num_frames/4`, `num_frames/2`, `3*num_frames/4`, `num_frames`.
6. There are four if-statements, but only three triangles drawn on the screen. What happened to the fourth triangle? Explain in at least once sentence.
7. Change the last if-statement so that the animation is able to draw and animate all four triangles.

{{< /checkpoint >}}


### [Animation Mystery 2]

{{< code-action "Run the" >}} `animate_2.py` **file.**

{{< checkpoint >}}
<!---frame-based -->
{{< write-action "Answer the following questions with your group." >}}


0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. Let's change some settings! Currently, the circle does not fit on the screen when it gets animated. Go to the `settings.py` file and change `START_X` and/or `START_Y` so that the animated circle is able to fit. While you're at it, let's also change `COLOR`. What values did you change `START_X` and/or `START_Y` to?
2. You'll notice that we used two for-loops in this example. For the first for-loop, trace through the code and fill out the table for every `i` and `new_size`. (HINT: you can split up the work on this with your tablemates.)
3. Calculate `max_size`. (HINT: you will need to reference the numbers in `settings.py`)
4. For the second for-loop, trace through the code and fill out the table for every `j` and `new_size`.(HINT: you can split up the work on this with your tablemates.)
5. Change the code so that the animation only grows half as big (aka the `max_size` is half as large). (HINT: you only need to change something in `settings.py`) What did you change?

{{< /checkpoint >}}


### [Animation Mystery 3]
{{< code-action "Run the" >}} `animate_3.py` **file.**

{{< checkpoint >}}
{{< write-action "Answer the following questions with your group." >}}

0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. What does the `clear()` function do in line 18? What happens if you remove `clear()`?
2. Change the code so that the animation moves five times as far. (HINT: you will need to change two lines of code in `draw_animation()`) What did you change?
3. What if you wanted to draw an animating square instead of a triangle? Write a new helper function in `parts.py` called `draw_square()` that takes two parameters: `side_len` and `color_name`. Then change line 15 in `animate_3.py` to `draw_square(side_len, color_name)`.
{{< /checkpoint >}}


### [Animation Mystery 4]
{{< code-action "Run the" >}} `animate_4.py` **file.**

{{< checkpoint >}}
{{< write-action "Answer the following questions with your group." >}}

0. What type of animation is this [Translate, Rotate, Scale, Frame-Based]?
1. This animation involves three if-conditional branches, and each branch causes a different speed! Why is the second branch faster than the first
branch? Why is the third branch faster than the second branch?
2. Change the code so that the animation turns in the opposite direction for all three conditional branches. Describe in one sentence which lines of code you changed and how you changed the code.

{{< /checkpoint >}}

<hr>

## [3] Deliverables

{{< deliverables "For this lab, you should:" >}}
- Submit your worksheet with answers to each checkpoint question.
{{< /deliverables >}}
