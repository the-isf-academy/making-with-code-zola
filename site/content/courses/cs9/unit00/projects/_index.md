---
Title: Project
slug: drawing
# draft: true
---

# Animation Project

In this project you will make an animated drawing (or a GIF!) using Python's turtle library.

It's up to you to make a drawing you actually care about making. Your teachers will help you choose a project that's a good level of challenge.

Here are a few examples from last year to get you started. More can be found at the `gallery` page.

{{< columns >}}

{{< figure src="images/courses/cs9/unit00/00_project_2021_edwin.gif" width="75%" title="by Edwin" >}}
<--->
{{< figure src="images/courses/cs9/unit00/00_project_2021_charlotte.gif" width="75%" title="by Charlotte" >}}
{{< /columns >}}




---

## [0] Planning Document

This is a big project, and you will get lost or frustrated if you don't do some planning up front. You are required to write a project planning document and get it approved by a teacher. Your planning document can be found in your Google Drive folder.


{{< write-action "Fill out your planning doc in your Google Drive folder." >}} First you must spend 10 minutes creating an inspiration board. 


**👀 Once you have completed your planning document, meet with a teacher to talk through your project.**


---

##  [1] Starter Code

For this project, your code will live in a git repository. It is your responsibility to regularly commit to your repository.

{{< code-action "Download your respository with starter code for your project." >}}
> replace the `yourGithubUsername` with your Github username.
>
> *example:*
>
> *`git clone https://github.com/the-isf-academy/project_animation_emmaqbrown.git`*


```shell
cd Desktop
cd cs9/unit_00
git clone https://github.com/the-isf-academy/project_animation_yourGithubUsername.git
```

It contains the following files:
- `project.py` When this program runs, it should draw your project.
- `settings.py` This is where you settings for your animation should be stored.
- `README.md` This is documentation for your project for other people who may want to use your project.
    

{{< code-action "Start coding your first milestone!" >}} With you design document approved by a teacher and your starter code downloaded, you're ready to start creating.

---

## [3] Criteria 

{{< columns >}}

{{< figure src="images/courses/cs9/unit00/00_project_2020_eric.gif" width="75%" title="by Eric" >}}
<--->
{{< figure src="images/courses/cs9/unit00/00_project_2020_austin.gif" width="75%" title="by Austin" >}}
{{< /columns >}}

**This project will be assessed on the following criteria:**
- project managment 
- iterative development
- readability 
- abstraction
- decomposition 

**For each criteria you will be assessed on a score from 0-3:**
- 0 - no evidence of the practice
- 1 - limited evidence of the practice
- 2 - adequate evidence of the practice
- 3 - substantial evidence of the practice

*To do well in this project, you should be able to concretely demonstrate that you can successfully do each practice*

---


### [Success Claims]

Successful computer scientists should be able to make the following claims:
- I can thoughtfully plan and manage a large computer science project.  
    - I can consider the components of my project before coding 
    - I can manage my time well and complete the project by the deadline
    - I can update my process journal on an ongoing basis to organize by thoughts for the next work day
- I can develop my project iteratively over time
    - I can track the development of my project by successfully committing to Github a minimum of each class work day 
    - I can write descriptive commit messages that accurately describe the changes made
    - I can systematically breakdown my project into smaller chunks  
- I can write code with readability in mind
    - I can write code as readable as possible for another CS student to understand
    - I can use descriptive names for modules, variables, and functions
    - I can write descriptive comments to describe complex pieces of the code
- I can effectively use the principle of abstraction to make my code more efficient and elegant
    - I can write a function with paramters
    - I can manipulate control flow with conditional statements
    - I can use loops to repeat commands
     can write functions with parameters
- I can effictively use the principle of decomposition to make my code more efficient and elegant
    - I can write functions to be used in different scenarios
    - I can write modules for different aspects of my project

*Keep the success claims in mind when coding your project.*

---

### [Scoring]

The project is scored out of 7. It will be calculated by adding the score from each criteria, then referencing the bands:
- 1 = 0
- 2 = 1
- 3 = 2-3
- 4 = 4-6
- 5 = 7-11
- 6 = 12-13
- 7 = 14-15

---

## [3] Deliverables

{{< deliverables  "Projects are due on Friday, 25 Novemeber." >}}


- `Unit 00 Animation Project: Planning Document` in your Google Drive folder
- `project_animation` repository containing the following files:
    - `project.py` When this program runs, it should draw your project.
    - `settings.py` This is where you settings for your animation should be stored.
    - `README.md` This is documentation for your project 
    - At least one additional module (written by you)

{{< code-action "Push your work to Github:" >}}
- `git status`
- `git add project.py`
    - you can add multiple files by putting a space inbetween each file
    - *e.g. `git add project.py settings.py`*
- `git status`
- `git commit -m "describe your drawing and your process here"`
  > be sure to customize this message, do not copy and paste this line
- `git push`
{{< /deliverables >}}




<!--
### Criterion A: Knowing, understanding, and computational thinking

Students appropriately apply computer science concepts and tools in context. On top of computer science concepts and tools, students apply computational thinking practices including habits such as writing pseudocode, developing iteratively, using abstractions, decomposing problems, and debugging.

In this unit, we explored the imperative programming paradigm as well as the basic building blocks of computation. This allowed us to control our programs with various forms of control flow (loops, functions, and conditional statements). Finally, we learned about abstraction and decomposition, which allows us to create programs that could be reused for a variety of different contexts with a range of parameters.

| Learning Claim                                                                                                 | Possible Forms of Evidence                                                                                                                                                                                                          |
|----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I can read and apply code documentation.                                                                       | <ul><li>At least 2 functions of the turtle library that we did not cover in class found by reading the Turtle documentation </li></ul>                                                                                                                             |
| I can manipulate control flow to meaningfully affect the outcome of my code. | <ul><li>At least one loop to repeat commands</li><li>At least one conditional to control the animation</li><li>At least one function with at least one input parameter</li><li>At least one context manager to affect the execution of a code block</li></ul>|
| I effectively use the principles of decomposition and abstraction to make my code more efficient and elegant. | <ul><li>Code decomposed into various helper functions</li><li>At least one function that is reused at least once in the code</li><li>For every function, the turtle starts and ends at the same point and position</li> <li>Code decomposed into at least one module</li></ul>|



### Criterion B: Planning and development
Students create personally meaningful projects through an iterative design cycle. Students’ work is grounded in a development plan which students create before beginning the project. Students document the development of their projects in order to create a record of decisions, assumptions, and lingering flaws. Students define the intended functionality and develop towards evaluation.

In this unit, you planned a project with a design document and also adjusted the scope of your project, which means you pivoted your project accordingly to meet the deadlines. Additionally, you were introduced to the concept of documentation via `README.md` files and git commits on Github.

| Learning Claim                                                                                                 | Possible Forms of Evidence                                                                                                                                                                                                          |
|----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I can thoughtfully plan a large computer science project.  | <ul><li>A thorough design document.</li><li>Updates to your project plan to account for challenges during development</li></ul>|
| I can document the development of my project using version control tools such as GitHub.  | <ul><li>At least 5 regular and descriptive git commits on your project</li><li>A description of a GitHub issue / bug you encountered, as well as an explanation of how you fixed it (you may include links that you used, such as StackOverflow). </li><li>Comments for each of the modules and functions in your project</li></ul>|


### Criterion D: Reflection on Tech and Society
Students demonstrate an understanding of their responsibility to society as technology creators by evaluating the implications of their work. Students investigate the applications of their work to specific problems or issues.
Throughout the unit, you explored what it means to express yourself and your identity via digital art.

| Learning Claim                                                                         | Possible Forms of Evidence                                                                      |
|----------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| I chose a theme that is personally meaningful to me to animate.                        | <ul><li>A final animation that is related to the theme you were inspired by in your planning document.</li></ul>  |
| I drew from another animation/GIF/drawing to inform my own drawing/animation process.  | <ul><li>A picture, piece of text, animation or video that informed your animation/drawing process.</li></ul>      |

 -->
