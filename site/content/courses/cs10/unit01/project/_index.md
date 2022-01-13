---
Title: Project
draft: false
---

# Unit Networking: Server Project

In this project, you will create a server using Banjo. It is up to you to create a server with a user in mind. 

## [0] Starter Code

{{< code-action "Clone the project repository" >}} in your `cs10\unit_00` folder. 

```shell
cd cs10/unit_00
git clone https://github.com/the-isf-academy/project-networking-YOUR-GITHUB-USERNAME.git
```

## [1] Planning Document

This is a big project, and you will get lost or frustrated if you don't do some planning up front.
Before you start working on your project, you are required to write a project proposal and get it
approved by a teacher. *You can find your planning doc in your Google Drive folder called "Unit Networking Project: Planning Document".*

## [2] Deliverables


- A `Unit Networking Project: Planning Document` - Google doc. This is where you will plan your project.
- A `project-networking` repository containing the following:
  - `\app`
    - `models.py` - This is where you will define your model.
    - `views.py` - This is where you will define your routes and endpoints.
  - `database.sqlite` - This is your database file. 
  - `README.md` This is documentation for your project.
- `Unit Networking Project: Self-Assessment` - Google doc. This is where you will self-assess your project.


### [Timeline]
Click below to see a detailed timeline for your class section.

#### cs10.1
{{< expand "cs10.1 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 14 Jan 2022 | Project Design Document  |
| 18 Jan 2022 | Work Day                |
| 20 Jan 2022 | Work Day                |
| 24 Jan 2022| Work Day                |
| 25 Jan 2022 | Due: Project Repository   |
| 28 Jan 2022 | Due: Self-assessment                 |

{{< /expand >}}

#### cs10.2

{{< expand "cs10.2 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 14 Jan 2022 | Introduction to Project |
| 17 Jan 2022| Work Day                |
| 19 Jan 2022 | Work Day                |
| 24 Jan 2022 | Work Day               |
| 26 Jan 2022 | Due: Project Repository   |
| 28 Jan 2022 | Due: Self-assessment                |
{{< /expand >}}

## [3] Starter Code

{{< code-action >}} The three empty files that you will implement are provided in the
`terminal-game-project` repo. Download it *onto your laptop*.

```shell
$ cd cs10/unit_01
$ git clone https://github.com/the-isf-academy/project-networking-YOUR-GITHUB-USERNAME.git
```



## [4] Self-Assessment
You are responsible for assessing your own project, though your teachers will let you know if they disagree and provide a final score.

In `Unit Networking Project: Self-Assessment`, you are required to explain how your project should be scored, and to give evidence to support your assessment. The rubric is based on claims that you should be able to make about your learning in this unit.

The self-assessment is broken down into three areas:
- Practices
    - test cases, reading documentation, readability, and debugging
- Concepts
    - model architecture and http requests
- Reflection

**To do well in this project, you should be able to concretely justify that you can do each practice and understand each concept by providing evidence from your code.**

### [Practices]
Each practice is something that a computer scientist does each time they approach a problem. You are required to self-assess your ability to do each practice.

For each practice you must provide the following:
- A score from 0-3
    - 0 - no evidence of the practice
    - 1 - limited evidence of the practice
    - 2 - adequate evidence of the practice
    - 3 - substantial evidence of the practice
- A justification of why you deserve that score
- Examples to support your justification


### [Concepts]
This project focused on key computer science concepts, abstraction and decomposition.
You are required to demonstrate your understanding of each concept through evidence based reflection.

For each concept you must provide the following:
- A score from 0-3
    - 0 - no to no evidence of the concept
    - 1 - limited evidence of the concept
    - 2 - adequate evidence of the concept
    - 3 - substantial evidence of the concept
- A justification of why you deserve that score
- Examples to support your justification
- A discussion of why each concept is important

### [Reflection]

As we reviewed networking, you explored how servers made and how user's interact with them. The reflection is space for you to think more deeply about how developers use layers when writing web based projects. 


## [5] Success Claims

Successful computer scientists should be able to make the following claims:
- I can consider a wide array of test cases
  - I can test the expected user scenarios
  - I can test or prevented unexpected user scenarios
- I can read and apply documentation 
  - I can reference the Banjo documentation
  - I can infer syntax from the provided examples
  - I can reference the Django documentation
- I can write code with readability in mind
  - I can use descriptive names for models, fields, methods, endpoints, and parameters
  - I can write descriptive comments
  - I can document my code in the README.md
- I can debug systematically
  - I can read and understand error messages
  - I can use the Banjo shell and print statements to effectively troubleshoot
- I can plan a model architecture
  - I can plan the necessary features of the model prior to coding 
  - I can write fields with appropriate data types
  - I can use methods to simplify code 
  - I can use the built-in model methods to appropriately affect the database
- I use write http requests 
  - I can appropriately use GET and POST requests
  - I can write endpoints with user experience in mind
  - I can provide descriptive messaging


**Keep the success claims in mind when coding your project and self-assessing yourself.**

## [6] Scoring

The project is scored out of 7.
- 1 point is assigned to the self-assessment
    - *By thoughtfully self-assessing your project and thoughtfully answering the reflection points, you will receive 1 point*
-  6 points are assigned to the practices & concepts
    - *To calculate your score for the practices & concepts, look at the following bands:*
    > 0 = 0-1
    >
    > 1 = 2-3
    >
    > 2 = 4-6
    >
    > 3 = 7-9
    >
    > 4 = 10-12
    >
    > 5 = 13-15
    >
    > 6 = 16-18

*Example score:*

    1 point for reflection and 
    5 points for practices & concepts (15/18)
    6 total points

