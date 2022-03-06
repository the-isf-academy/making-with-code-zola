---
Title: Project
# draft: True

---

# Unit 01 Data Science Project
The final project for this unit will be a small research project. Working with the data science tools we explored this unit, you will ask and answer a question using data we collected about your digital habits. You will present your findings to your peers.

To be successful in this project, you will need to find a question that is both interesting to you and answerable (at least in part) with data from your chosen dataset. Your teachers will help you make sure your question achieves that.

Here is an [example project juptyer notebook file](https://github.com/the-isf-academy/project-data-science-example/blob/master/project.ipynb). It has been adapted from a previous student's work. As such, the project had a different dataset requirement.

---

## [0] Deliverables 

- Planning proposal in your Google Drive folder 
- Project repository containing the following files:
    - `dataset` - A `.csv` file containg your dataset
    - `project.ipynb` - This Jupyter notebook should contain all the code to run your research analysis as well as a discussion of your results 
- 2-3 Google slides presenting your findings
- Self-assessment document in your Google Drive folder 


### [Project Proposal]
For this project, you must write a project proposal outlining your overarching research question, sub-questions, and action steps.

**You should complete this proposal in 1-2 class periods** 

Once you have completed the proposal, meet with a teacher to talk through your proposal. 


### [project.ipynb]
This document is where your code and analysis will be located. To complete your project, you should 
fill out the project.ipynb Jupyter notebook with each of the following sections:

- Introduction - an overarching question about social media and a brief background of why this
  question is interesting
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

### [Research Presentation]
In addition to performing data analysis to answer an overarching question, you will share your results and discussion with a short presentation.

To do this, you will need to:
- create 2-3 slides outlining your results and discussion 
- consider how to best communicate your results and discussion 

---

## [1] Timeline

Click below to see a detailed timeline for your class section.

#### cs9.1
{{< expand "cs9.1 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 8 March 2022  | Introduction to Project |
| 9 March 2022  | Start Design Document & One-on-One with teacher       |
| 10 March 2022 | Complete Design Document & One-on-One with teacher         |
| 15 March 2022 | Work Day                |
| 22 March 2022 | Work Day                |
| 23 March 2022 | Work Day                |
| 24 March 2022 | Work Day     |
| 29 March 2022 | Work Day     |
| 01 April 2022 | DUE: Submit Code Repository    |
| 06 April 2022 | DUE: Self-assessment    |
{{< /expand >}}

#### cs9.2

{{< expand "cs9.2 Timeline" >}}

| Date        | Agenda                  |
|-------------|-------------------------|
| 7 March 2022  | Introduction to Project |
| 10 March 2022  | Start Design Document & One-on-One with teacher       |
| 11 March 2022 | Complete Design Document & One-on-One with teacher         |
| 15 March 2022 | Work Day                |
| 17 March 2022 | Work Day                |
| 21 March 2022 | Work Day                |
| 24 March 2022 | Work Day     |
| 25 March 2022 | Work Day     |
| 29 March 2022 | DUE: Submit Code Repository    |
| 31 March 2022 | DUE: Self-assessment    |
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
    - iterative development, reading documentation, planning, reflection 
- Concepts
    - science communication
    - data visualization 
    - research question  

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


### [Reflection]

Throughout the unit, you explored what it means to express yourself and your identity via digital art. The reflection is space for you to explore your responsibility to society as technology creators by evaluating the implications of your work.

*It is marked purely based on completion and demonstration of effort.*


## [4] Success Claims

Successful computer scientists should be able to make the following claims:
- I can thoughtfully plan a large computer science project. 
- I can develop my project iteratively over time
    - I can track the development of my project by committing to Github consistently throughout my project.
    - I can systematically breakdown my project into smaller chunks   
- I can analyze and visualize data to answer questions I have about what the data means.                   	
    - a summary statistic (mean, median, mode) describing the data
    - a plot generated to answer a question
    - explanations of why a statistic or plot answers a question
- I can read and understand documentation
    - reading the offical documentation for Pandas and Matplotlib
    - using online resources such as StackOverflow 
- I can use appropriate data structures to capture the form of my data and to serve my analytical purpose. 
    - use of a data structure (i.e. list, dict, dataframe) which is appropriate for what you want to store
    - code looping through a data structure in order to access/change elements inside the data structure
- I can use functions to abstract and decompose computational processes.                    
    - a function that transforms data into a more useful format (i.e. filtering)
    - a pair of functions where one function generates an output which is then used as the input of the second function                               	
- I can select and clean data to serve as a source for my analysis.                                 	
    - handling of bad data by cleaning the data beyond what’s provided (removing the data that is blank or determining that an outlier is actually bad data)
    - Combinations or reorganizations of data that explore new relationships
    - different versions of code that use different selections of data
    - Justifications of why particular data was/wasn't selected and how that choice impacted the results
- I evaluate the analytical choices I make by producing evidence to show that my choices are sound. 	
    - a test to make sure that your code is doing what it's supposed to (filtering a dataframe to check for values, producing counts to make sure data was filtered, etc.)
    - a different version of some part of your code that explores an alternative approach
    - an explanation of a choice you made in analysis in the Methods section of your project                                                      
- I understand that data analysis can impact understanding and decision-making in the world 
    - discussion of the underlying benefits of your quantitative analysis
    - discussion of how your research fits into a larger context
    - a call to action for how the answers to your question should impact decision making at the community or personal level
- I can identify limitations and potential improvements of my research
    - discussion of the limitations of your quantitative analysis
    - possible approaches to addressing the limitation
    - identification of biases present in your analysis
    - an outline of future steps for research in your area


**Keep the success claims in mind when coding your project and self-assessing yourself.**

## [5] Scoring

The project is scored out of 7.
- 1 point is assigned to the self-assessment and reflection
    - *By thoughtfully answering the prompts and putting effort into your response, you will receive 1 point*
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

    5 points for practices & concepts (15/18)
    6 total points





