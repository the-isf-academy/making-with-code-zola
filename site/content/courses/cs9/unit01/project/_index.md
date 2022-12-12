---
Title: Project
draft: True
# headless: true
---

# Unit 01 Data Science Project
The final project for this unit will be a small research project. Working with the data science tools we explored this unit, you will ask and answer a question using data we collected about your digital habits or media consumption. You will present your findings to your peers.

To be successful in this project, you will need to find a question that is both interesting to you and answerable (at least in part) with data from your chosen dataset. Your teachers will help you make sure your question achieves that.

Here is an [example project juptyer notebook file](https://github.com/the-isf-academy/project-data-science-example/blob/master/project.ipynb). It has been adapted from a previous student's work. As such, the project had a different dataset requirement.


{{< aside "ATTN: Online learning change" >}}

Due to difficulties of online learning, students will not be required to complete a self-assessment. 

As such, we have adjusted the grading bands. Please see the below ***Scoring*** section, for the updates.

{{< /aside >}}


---



## [0] Deliverables 

- Planning proposal in your Google Drive folder 
- Project repository containing the following files:
    - `dataset` - A `.csv` file containg your dataset
    - `project.ipynb` - This Jupyter notebook should contain all the code to run your research analysis as well as a discussion of your results 
- Self-assessment document in your Google Drive folder 


### [Project Proposal]
For this project, you must write a project proposal outlining your overarching research question, sub-questions, and action steps.

**You should complete this proposal in 1-2 class periods.** Once you have completed the proposal, meet with a teacher to talk through your proposal. 


### [project.ipynb]
This document is where your code and analysis will be located. To complete your project, you should 
fill out the project.ipynb Jupyter notebook with each of the following sections:

- Introduction - an overarching question about your digital habits or media consumption
- Data - a description of the data you use in your analysis and a justification of how columns were
  chosen
- Analytic Sub-Question(s) - sub-questions which can be answered (at least in part) by a quantitative
  insight
- Methods - a description and justification of the methods you used to restructure and analyze your data
- Results - an answer to each subquestion with a plot or statistic, justification of why that
  plot/statistic answers the question, and an exploration of the limitations of the plot/stat to
  answer the question
- Discussion - A discussion about the overarching question and how the sub-questions contribute to an 
  understanding of the overall question

---

## [1] Timeline

Click below to see a detailed timeline for your class section.

#### cs9.1
{{< expand "cs9.1 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 10 March 2022  | Introduction to Project       |
| 11 March 2022 | Pull Data & Start Design Document         |
| 15 March 2022 |Pull Data & Design Document        |
| 17 March 2022 | Design Document & One-on-One with teacher                |
| 21 March 2022 | One-on-One with teacher & Work Day                |
| 24 March 2022 | Work Day     |
| 25 March 2022 | Work Day     |
| 29 March 2022 | Work Day    |
| 31 March 2022 | Work Day    |
| 4 April 2022 | DUE: Submit Code Repository    |


{{< /expand >}}

#### cs9.2

{{< expand "cs9.2 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 8 March 2022  | Introduction to Project |
| 9 March 2022  | Pull Data & Start Design Document       |
| 10 March 2022 | Design Document & One-on-One with teacher         |
| 15 March 2022 | Design Document & One-on-One with teacher                |
| 22 March 2022 | Work Day                |
| 23 March 2022 | Work Day                |
| 24 March 2022 | Work Day     |
| 29 March 2022 | Work Day     |
| 01 April 2022 | Work Day    |
| 06 April 2022 | DUE: Submit Code Repository    |

{{< /expand >}}

---

## [2] Starter Code

{{< code-action "Download the starter code for the project in the" >}} 
`project-data-science` repo. 

```shell
cd desktop/cs9/unit_01
git clone https://github.com/the-isf-academy/project-data-science-YOUR-GITHUB-USERNAME.git
```

---

## [3] Self-Assessment
You are responsible for assessing your own project, though your teachers will let you know if they disagree and provide a final score.

In `Unit 01 Data Science Project: Self-Assessment`, you are required to explain how your project should be scored, and to give evidence to support your assessment. The rubric is based on claims that you should be able to make about your learning in this unit.

The self-assessment is broken down into two sections:
- Practices
    - planning 
    - iterative development 
    - reading documentation 
- Concepts
    - data structures  
    - data analysis 
    - data discussion 


**To do well in this project, you should be able to concretely justify that you can do each practice and understand each concept by providing evidence from your code.**

### [Practices]
Each practice is something that a computer scientist does each time they approach a problem. You are required to self-assess your ability to do each practice.

For each practice you must provide the following:
- A score from 0-3
    - 0 - no to no evidence of the concept
    - 1 - limited evidence of the concept
    - 2 - adequate evidence of the concept
    - 3 - substantial evidence of the concept
- A justification of why you deserve that score
- Examples to support your justification

### [Concepts]
This project focused on key computer science data concepts. You are required to demonstrate your understanding of each concept through evidence based reflection.

For each concept you must provide the following:
- A score from 0-3
    - 0 - no to no evidence of the concept
    - 1 - limited evidence of the concept
    - 2 - adequate evidence of the concept
    - 3 - substantial evidence of the concept
- A justification of why you deserve that score
- Examples to support your justification
- A short discussion of why each concept is important

## [4] Success Claims

Successful computer scientists should be able to make the following claims:
- I can thoughtfully plan a data science project. 
    - an appropriate research question and related sub-questions 
    - a discussion of why that the overarching question is important to analyze 
    - action steps to answering each question 
- I can develop my project iteratively over time
    - I can track the development of my project by committing to Github consistently throughout my project.
    - I can systematically breakdown my project into smaller chunks   
- I can read and understand documentation
    - reading the offical documentation for Pandas and Matplotlib
    - using online resources such as StackOverflow 
- I can use appropriate data structures to capture the form of my data and to serve my analytical purpose. 
    - use of a data structure (i.e. list, dict, dataframe) which is appropriate for what you want to store
    - code looping through a data structure in order to access/change elements inside the data structure
    - Combinations or reorganizations of data that explore new relationships  
- I can analyze and visualize data to answer questions I have about what the data means.                   	
    - a summary statistic (mean, median, mode) describing the data
    - a plot generated to answer a question
    - explanations of why a statistic or plot answers a question
- I can discuss the findings of my research and evaluate its limitations and impacts
    - discussion of the limitations of your quantitative analysis
    - identification of biases present in your analysis
    - discussion of the underlying benefits of your quantitative analysis
    - discussion of how your research fits into a larger context
    - a call to action for how the answers to your question can impact personal decision making

**Keep the success claims in mind when coding your project and self-assessing yourself.**

## [5] Scoring

The project is scored out of 7. 

*To calculate your score for the practices & concepts, look at the following bands:*

> 0 = 0
>
> 1 = 1
>
> 2 = 2-3
>
> 3 = 4-5
>
> 4 = 6-8
>
> 5 = 9-12
>
> 6 = 13-15
>
> 7 = 16-18




