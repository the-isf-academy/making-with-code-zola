---
Title: "Project"
# draft: true
---

# Networking: Social Collaboration Project

In this project, you will create a server using Banjo. It is up to you to create a server with a user in mind. 

---

## [0] Planning Document

This is a big project, and you will get lost or frustrated if you don't do some planning up front.
Before you start working on your project, you are required to complete the Project Planning Google sheet. 

*You can find your planning doc in your Google Drive folder called "Unit Networking Project: Planning Document".*

{{< code-action >}} **Make a copy of [THIS SHEET]().**

0. share it with your group member(s)
0. share it with Ms. Brown & Ms. Genzlinger

{{< write-action "Fill out the 'Planning' sheet." >}} Once you're comp

---

## [1] Starter Code

{{< code-action "Clone the project repository" >}} in your `cs10\unit_00` folder. 

```shell
cd cd ~/desktop/making_with_code/cs10/unit00_networking/
git clone https://github.com/the-isf-academy/project-networking-YOUR-GITHUB-USERNAME.git
```

It contains the following files:
- `project.py` When this program runs, it should draw your project.
- `settings.py` This is where you settings for your animation should be stored.
- `README.md` This is documentation for your project for other people who may want to use your project.
    

{{< code-action "Start coding your first milestone!" >}} With you design document approved by a teacher and your starter code downloaded, you're ready to start creating.

---

## [2] Criteria 
You are responsible for assessing your own project, though your teachers will let you know if they disagree and provide a final score.

In `Unit Networking Project: Self-Assessment`, you are required to explain how your project should be scored, and to give evidence to support your assessment. The rubric is based on claims that you should be able to make about your learning in this unit.


**This project will be assessed on the following criteria:**
- 
- iterative development
- group collaboration 
- model architecture
  - readability 
  - abstraction
- api architecture
  - readability
  - error handeling 

**For each criteria you will be assessed on a score from 0-3:**
- 0 - no evidence of the practice
- 1 - limited evidence of the practice
- 2 - adequate evidence of the practice
- 3 - substantial evidence of the practice

*To do well in this project, you should be able to concretely demonstrate that you can successfully do each practice*

---

### [Success Claims]

Successful computer scientists should be able to make the following claims:
- I can write code with error handeling in mind 
  - I can test the expected user scenarios
  - I can test or prevented unexpected user scenarios
- I can write code with readability in mind
  - I can use descriptive names for models, fields, methods, endpoints, and parameters
  - I can write descriptive comments
  - I can document my code in the README.md
- I can plan a model architecture
  - I can reference the Banjo documentation
  - I can plan the necessary features of the model prior to coding 
  - I can write fields with appropriate data types
  - I can use methods to simplify code 
  - I can use the built-in model methods to appropriately affect the database
- I use write api architecture 
  - I can appropriately use GET and POST requests
  - I can write endpoints with user experience in mind
  - I can provide descriptive JSON messaging


*Keep the success claims in mind when coding your project and self-assessing yourself.*

---

### [Scoring]

The project is scored out of 7. It will be calculated by adding the score from each criteria, then referencing the bands:
- 1 = 0
- 2 = 1-2
- 3 = 3-5
- 4 = 6-9
- 5 = 10-12
- 6 = 13-14
- 7 = 15

---

## [3] Deliverables

{{< deliverables  "Projects are due on Friday, 25 Novemeber." >}}

- A `Unit Networking Project: Planning Document` - Google doc. This is where you will plan your project.
- A `project-networking` repository containing the following:
  - `\app`
    - `models.py` - This is where you will define your model.
    - `views.py` - This is where you will define your routes and endpoints.
  - `database.sqlite` - This is your database file. 
  - `README.md` This is documentation for your project.
- `Unit Networking Project: Self-Assessment` - Google doc. This is where you will self-assess your project.


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




