---
Title: Project
# draft: true
---

# Unit 00 Drawing Project

In this project you will make an animated drawing (or a GIF!) using Python's turtle library. 

It's up to you to make a drawing you actually care about making. Your teachers will help you choose a project that's a good level of challenge.



## [0] Design Document

This is a big project, and you will get lost or frustrated if you don't do some planning up front. You are required to write a project design document and get it approved by a teacher.

👀 **Before you start the design document, spend 10-15 minutes brainstorming ideas for your project.** Use the internet to search for inspiration.

{{< expand "Inspiration from last year" >}}

Here are a few examples from last year to get you started. More can be found at the `gallery` page.

{{< columns >}}

{{< figure src="images/courses/cs9/unit00/00_project_2020_eric.gif" width="100%" title="by Eric Mok" >}}
{{< figure src="images/courses/cs9/unit00/00_project_2020_james.gif" width="100%" title="by James Castley" >}}
<--->
{{< figure src="images/courses/cs9/unit00/00_project_2020_austin.gif" width="100%" title="by Austin Lee" >}}
{{< figure src="images/courses/cs9/unit00/00_project_2020_karissa.gif" width="100%" title="by Karissa Mirza" >}}
{{< /columns >}}

{{< /expand >}}

{{< write-action "With an idea in mind, fill out your design doc in your Google Drive folder." >}}


{{< checkpoint >}}
**Once you have completed your design document, meet with a teacher to talk through your project.** 

{{< /checkpoint >}}



## [1] Deliverables 

- A `Unit 00 Animation Project: Design Document` in your Google Drive folder 
- A `project-animation` repository containing the following files:
    - `project.py` When this program runs, it should draw your project. 
    - `settings.py` This is where you settings for your animation should be stored. 
    - `README.md` This is documentation for your project for other people who may want to use your project.
    - At least one additional module (written by you)
- `Unit 00 Animation Project: Self-Assessment` - This is where you will self-assest your final project. 
- Your notebook with your sketches and project process journal 

### [Timeline]
#### cs9.1
{{< figure src="images/courses/cs9/unit00/00_project_cs9_1.png" width="100%" >}}
#### cs9.2
{{< figure src="images/courses/cs9/unit00/00_project_cs9_2.png" width="100%" >}}



##  [2] Starter Code

For this project, your code will live in a git repository. It is your resopnsiblity to regularly commit to your repository. 

{{< code-action "Download your respository with starter code for your project." >}} 
> replace the `YOUR-GITHUB-USERNAME` with your Github username.
>
> *example:*
>
> *`git clone https://github.com/the-isf-academy/project-animation-emmaqbrown.git`*


```shell
cd Desktop
cd cs9/unit_00
git clone https://github.com/the-isf-academy/project-animation-YOUR-GITHUB-USERNAME.git
```

{{< code-action "Start coding your first milestone!" >}} With you design document approved by a teacher and your starter code downloaded, you're ready to start creating. 


## [3] Self-Assessment
You are responsible for assessing your own project, though your teachers will let you know if they disagree and provide a final score. 

In `Unit 00 Animation Project: Self-Assessment`, you are required to explain how your project should be scored, and to give evidence to support your assessment. The rubric is based on claims that you should be able to make about your learning in this unit. 

The self-assessment is broken down into three areas:
- Practices
    - planning, iterative development, test cases, and readability
- Concepts
    - abstraction and decomposition
- Reflection

**To do well in this project, you should be able to concretely justify that you can do each practice and understand each concept by providing evidence from your code.** 

### [Practices]
Each practice is something that a computer scientist does each time they approach a problem. You are required to self-assess your ability to do each practice. 

For each practice you must provide the following:
- A score from 0-3
    - 0 - little to no evidence of practice 
    - 1 - below average evidence of practice 
    - 2 - above average evidence of practice
    - 3 - outstanding evidence of practice
- A justification of why you deserve that score 
- Examples to support your justification 


### [Concepts]
This project focused on key computer science concepts, abstraction and decomposition.
You are required to demonstrate your understanding of each concept through evidence based reflection. 

For each concept you must provide the following:
- A score from 0-5
    - 0 - little to no understanding or implementation of the concept
    - 1 - below average understanding or implementation the concept
    - 2 - above average understanding or implementation the concept
    - 3 - outstanding understanding or implementation the concept
- A justification of why you deserve that score 
- Examples to support your justification 
- A discussion of why each concept is important 

### [Reflection]

Throughout the unit, you explored what it means to express yourself and your identity via digital art. The reflection is space for you to explore your resopnsiblity to society as technolgogy creators by evaluating the implications of your work. 

*It is graded purely based on completion and demonstration of effort.*



## [4] Sucess Claims 

Each project will look entirely different and have their individual measure of success. 

However, all successful computer scientists should be able to make the following claims: 
- I can thoughtfully plan a large computer science project.  
- I can develop my project iteratively over time 
    - I can track the development of my project by committing to Github consistently throughout my project.
    - I can systematically breakdown my project into smaller chunks  
- I can write code with readability in mind
    - I can use describe names for variables, functions, and modules
    - I can document my code in the README.md
- I can effectively use the principle of abstraction to make my code more efficient and elegant 
    - I can write a function with at least one paramter
    - I can use manipulate control flow with conditionals 
    - I can use loops to repeat commands
- I can effictively use the principle of decomposition to make my code more efficient and elegant
    - I can write functions to be used in different scenarios
    - I can write modules for different aspects of my project

**Keep the success claims in mind when coding your project and self-assessing yourself.**




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
