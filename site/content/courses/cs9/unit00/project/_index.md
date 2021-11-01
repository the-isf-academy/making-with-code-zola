---
Title: Project
draft: true
---

# Unit 00 Drawing Project

In this project you will make an animated drawing (or, in Gen Z terminology, a GIF!) using Python's turtle library. That's the whole assignment.

It's up to you to make a drawing you actually care about making. Your teachers will help you choose a project that's a good level of challenge, and will support you every step of the way. 

## Starter Code

{{< code-action >}} Starter code for the project is provided in the
`project-animation` repo. Download it *onto your laptop*.

```shell
$ cd cs9/unit_00
$ git clone https://github.com/the-isf-academy/project-animation-YOUR-GITHUB-USERNAME.git
```


To get started, you will link your design document into your `README.md` file.

{{< code-action "Find your project design document in your Google Drive and link in your" >}} `README.md`.

> Use the follow syntax to create a hyperlink:
> 
> `[9. Version Control](www.cs.fablearn.org)`
>
> This will result in: [9. Version Control](www.cs.fablearn.org)


## Design Document

This is a big project, and you will get lost or frustrated if you don't do some planning up front. Before you start working on your project, you are required to write a project proposal and get it approved by a teacher. *You can find your design doc in your Google Drive folder.*

Once you have completed the above, meet with a teacher to talk through your plan. Don't start programming until you get your plan approved, or you might have to change it.

## Deliverables 

- A design document in your Google Drive folder 
- A project repository containing the following files:
    - `project.py` When this program runs, it should draw your project. 
    - `settings.py` This is where you settings for your animation should be stored. 
    - `README.md` This is documentation for your project for other people who may want to use your project.
    - `assessment.md` This is where you will self-assest your final project. 
    - At least one additional module (written by you)
- At least 5 substantial Git commit messages, each explaining what you've changed and why.

## Timeline
### cs9.1
{{< figure src="images/courses/cs9/unit00/00_project_cs9_1.png" width="100%" >}}
### cs9.2
{{< figure src="images/courses/cs9/unit00/00_project_cs9_2.png" width="100%" >}}

## Assessment
You are responsible for assessing your own project, though your teachers will let you know if they
disagree. In `assessment.md`, you are required to explain how your project should be scored, and
to give evidence to support your assessment. The rubric is based on claims that you should be able
to make about your learning in this unit. Each of these claims comes with examples of evidence that
would show that you can make the claim about your learning.

**To do well in this project, you should be able to concretely justify that you have achieved each of
the learning claims.** So, if the rubric says you should be able to manipulate control flow and that 
an example of doing that would be to use a loop, then you should use loops in your project and point
to them in your self-assessment.
If the rubric says you should be able to thoughtfiully plan a large project and that an example of that
is a thorough design document, you should create a detailed design document and discuss in your self-assessment
how this design document helped you create your project.

Since this is your first project, here's a guide for using the rubric:
- Read the learning claims of the criterion for this unit in the rubric and consider how they relate to
the description of the criterion.
- For each learning claim in the criterion:
    - Evidence: Identify 1-5 elements of your project that provide evidence for the learning claim.
    - Reasoning: Provide specific reasoning that presents how the piece(s) of evidence you identified
    support the claim about your learning.
- Determine the level between 1-8 that represents your overall learning in the criterion based on the
evidence and reasoning you provided for the learning claims of the criterion.

## Rubric 

Each project will be assessed with a rubric tailored to the skills and concepts the project targets.
This project is focused on developing the skills learned throughout the drawing unit. 


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


