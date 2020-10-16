---
title: 6. Decomposition
type: labs
draft: true
---

# Decomposition Lab

{{< devnote >}}
Replace the ISF Academy repo links
{{< /devnote >}}

## A. Review of Modules Lab

Now we are going to download a repository made by a CS9 student from last year, Iris (CS9, 2019) for her unit 0 drawing project. The CS teaching team adapted to include animations. She drew Winwin from NCT and decided to do Winwin's side profile drawing with his name in block letters.

This project will be similar to what you yourselves will make for the unit project.


Make sure you are in `unit_00` and then download it using git:

```shell
    TEA-JWOLF:unit_00 jwolf$ git clone https://github.com/the-isf-academy/unit_00_project_Iris.git
```

There are quite a few modules being used here! Use `tree`, the `READ.ME`, Atom, and the terminal to explore her project.

{{< checkpoint >}}
Once you've fully explored her code, answer the following questions:

- What command do you use to run the still version of her code?
```
TEA-JWOLF:unit_00_project_Iris jwolf$ ______
```

- What command do you use to run the animated version of her code?
```
TEA-JWOLF:unit_00_project_Iris jwolf$ ______
```
- Iris has four modules in her project. Name the modules here, and describe the purpose of each module in one function.
```
There are four modules and two main files. The four modules are:

    1. This module is called _____, and it includes functions related to ____. It is used by ____.

    2. This module is called _____, and it includes functions related to ____. It is used by ____.

    3. This module is called _____, and it includes functions related to ____. It is used by ____.

    4. This module is called _____, and it includes functions related to ____. It is used by ____.
```

- Which module would you edit in order to adjust the `sf` variable?
```
  The module I would change is _____.
```
{{< /checkpoint >}}


## B. Intro to Decomposition

{{< include_resource "resource_decomposition" >}}

First, let's take a look at how Iris decomposed her still image. Then, we'll see how we decomposed the animation.

### Still Image

Iris decided to tackle the image by drawing the figure and then the letters.

#### Figures
- How many functions are in the figures module?
- Where is `draw_figure() ` actually called in her project?
- How could Iris have decomposed her `draw_figure()` function further?  

#### Letters
- Why do you think Iris chose to create a separate module for letters?
- Where is `draw_W() ` actually called in her project?

#### Settings
- Iris chose to write functions that accepted a parameter called `settings.sf`. Can you find out where it is being defined, and can you tell what sf stands for?
- Change `settings.sf` to any number you like. How does this affect her still image when you run `no_animation.py`?

You might also have noticed that this module uses `fillcolor` to fill in shapes. You could open the [turtle documentation](https://docs.python.org/3.7/library/turtle.html?highlight=turtle#turtle.fillcolor) and read about how filling works.


### Animation

#### Main

#### Draw Stationary

#### Animate

## C. More Animations
Now we are going to download a repository made by another CS9 student from last year, Jethro (CS9, 2019) for his unit 0 drawing project. The CS teaching team adapted to include animations. He drew a cat with a paw.

This project will be similar to what you yourselves will make for the unit project.


Make sure you are in `unit_00` and then download it using git:

```shell
    TEA-JWOLF:unit_00 jwolf$ git clone https://github.com/the-isf-academy/unit-0-drawing-yobamos912
```

Now answer the following questions with your team. You will be asked to change parts of Jethro's code!

### Animation Set Up
- What does the for-loop in  `main()` do?
- How is `draw_stationary()` different from the code in `no_animation.py`?
- What does `s.whisker_len` do? Where is it being defined?

### Animation Mystery 1
<!-- - rotation -->
- Why are there two loops back to back? (Interpolation)
- Change the speed of the rotation.

### Animation Mystery 2
<!-- - resize -->
- To clear or not to clear ...

### Animation Mystery 3
<!-- - translation (failed) -->
- Why does the translation fail?



## Deliverables

- Each student should submit a Google Doc with answers to the questions above.
