---
Title: Project
---

# Unit 01 Data Science Project
The final project for this unit will be a small research project. Working with the data science tools
we explored this unit, you will ask and answer a question using data we collected about our digital
lives. You will present your findings to your peers.

To be successful in this project, you will need to find a question that is both interesting to you 
and answerable (at least in part) with data from the social media dataset. Your teachers will help 
you make sure your question achieves that.

## Starter Code

{{< code-action >}} Starter code for the project is provided in the
`project-data-science` repo. Download it *onto your laptop*.

```shell
$ cd cs9/unit_01
$ git clone https://github.com/the-isf-academy/project-data-science-YOUR-GITHUB-USERNAME.git
```

## Project Proposal (Google Doc)
For this project, your proposal will be the first three sections of the final project (Introduction, 
Data, Analytic Sub-Question).

**You should complete this proposal in 1-2 class periods** Before you start working on your project,
you are required to write a project proposal and get it approved by a teacher. *You can find your
design doc in your Google Drive folder.*

Once you have completed the above, meet with a teacher to talk through your proposal. Don't start
programming until you get your proposal approved, or you might have to change it.

## Project (project.ipynb)
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

## Research Communication (communication.jpeg)
In addition to performing data analysis to answer a question, you will share your results and
discussion with the wider community in the form of an Instagram post, a flyer, a YouTube video, or
some other broadcast medium.

To do this, you will need to consider:

- the audience who will find your results most interesting (your peers? younger students? teachers?)
- what platform that audience uses (digital? physical?)
- how to best communicate your results and discussion with that audience

## Deliverables 

- A proposal document in your Google Drive folder 
- A project repository containing the following files:
    - `project.ipynb` - This Jupyter notebook should contain all the code to run your research analysis
      as well as a discussion of your results (described above).
    - `assessment.md` - This is where you will self-assess your unit project. 
    - `communication.jpeg` - Photographic evidence of how you shared your analysis (i.e. a screenshot of your Instagram post, a screenshot of your flyer, etc.)
- At least 5 substantial Git commit messages, each explaining what you've changed and why.

## Example Project
Here is an [example project proposal](https://docs.google.com/document/d/1bx8hcyBM8RntT2Qa8nGFAoOSiIPRXHM8KCpq3kwzDmw/edit)
and an [example repository](https://github.com/the-isf-academy/unit-1-project-teaching-team) containing
all of the elements of a complete project (minus the research communication).

## Timeline
### cs9.1
- [Milestone 1] March 15, 2021 - Finalize proposal
- [Milestone 2] March 19, 2021 - 1 subquestion completed
- [Milestone 3] March 26 - 2 subquestions completed
- **[Due Date] March 29, 2021 - All deliverables due**

{{< figure src="images/courses/cs9/unit01/01_project_calendar_cs9_1.png" width="100%" >}}
### cs9.2
- [Milestone 1] March 12, 2021 - Finalize proposal
- [Milestone 2] March 18, 2021 - 1 subquestion completed
- [Milestone 3] March 23, 2021 - 2 subquestions completed
- **[Due Date] March 26, 2021 - All deliverables due**

{{< figure src="images/courses/cs9/unit01/01_project_calendar_cs9_2.png" width="100%" >}}

## Assessment
You are responsible for assessing your own project, though your teachers will let you know if they
disagree. In `assessment.md`, you are required to explain how your project should be scored, and
to give evidence to support your assessment. The rubric is based on claims that you should be able
to make about your learning in this unit. Each of these claims comes with examples of evidence that
would show that you can make the claim about your learning.

As a reminder, here's a guide for using the rubric:
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

 > Students appropriately apply computer science concepts and tools in context. On top of computer science concepts and tools, students apply computational thinking practices including habits such as writing pseudocode, developing iteratively, using abstractions, decomposing problems, and debugging.

In this unit, we covered some of the core ideas of computational thinking (like inputs/outputs of functions) and some fundamental tools of computer science (like data types, variables, and data structures).

| Learning Claim                                                                                           	| Possible Forms of Evidence                                                                                                                                                                                                                                                       	|
|----------------------------------------------------------------------------------------------------------	|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| I can analyze and visualize data to answer questions I have about what the data means.                   	| <ul><li>a summary statistic (mean, median, mode) describing the data</li><li>a plot generated to answer a question</li><li>explanations of why a statistic or plot answers a question</li><li>use of a feature from Pandas or Matplotlib that we didn't cover in class</li></ul> 	|
| I can use appropriate data structures to capture the form of my data and to serve my analytical purpose. 	| <ul><li>use of a data structure (i.e. list, dict, dataframe) which is appropriate for what you want to store</li><li>code looping through a data structure in order to access/change elements inside the data structure</li></ul>                                                	|
| I can use functions to abstract and decompose computational processes.                                   	| <ul><li>a function that transforms data into a more useful format (i.e. filtering)</li><li>a pair of functions where one function generates an output which is then used as the input of the second function</li></ul>                                                           	|

### Criterion B: Planning and development
> Students create personally meaningful projects through an iterative design cycle. Students’ work is grounded in a development plan which students create before beginning the project. Students document the development of their projects in order to create a record of decisions, assumptions, and lingering flaws. Students define the intended functionality and develop towards evaluation.

From idea to communication, data science requires significant forethought: what data will you use? How will you answer your question? Who will care about the answer?

| Learning Claim                                                                                                 | Possible Forms of Evidence                                                                                                                                                                                                          |
|----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I can thoughtfully plan a large computer science project.  | <ul><li>A thorough design document.</li><li>Updates to your project plan to account for challenges during development</li></ul>|
| I can document the development of my project using version control tools such as GitHub.  | <ul><li>At least 5 regular and descriptive git commits on your project</li><li>A description of a GitHub issue / bug you encountered, as well as an explanation of how you fixed it (you may include links that you used, such as StackOverflow). </li><li>Comments for each of the modules and functions in your project</li></ul>|

### Criterion C: Evaluation
> Students produce evidence of a testing plan that evaluates the main areas of functionality of the product and reflect on the development process as well as a proposal for further development to improve the shortcomings of the current product.

Data science research requires us to evaluate our work from data selection to data anlysis to data visualization to
make sure our work is accurate and ethical.

| Learning Claim                                                                                    	| Possible Forms of Evidence                                                                                                                                                                                                                                                                                                                                                                                                                  	|
|---------------------------------------------------------------------------------------------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| I can select and clean data to serve as a source for my analysis.                                 	| <ul><li>handling of bad data by cleaning the data beyond what’s provided (removing the data that is blank or determining that an outlier is actually bad data)</li><li>Combinations or reorganizations of data that explore new relationships</li><li>different versions of code that use different selections of data</li><li>Justifications of why particular data was/wasn't selected and how that choice impacted the results</li></ul> 	|
| I evaluate the analytical choices I make by producing evidence to show that my choices are sound. 	| <ul><li>a test to make sure that your code is doing what it's supposed to (filtering a dataframe to check for values, producing counts to make sure data was filtered, etc.)</li><li>a different version of some part of your code that explores an alternative approach</li><li>an explanation of a choice you made in analysis in the Methods section of your project</li></ul>                                                           	|

### Criterion D: Reflection on Tech and Society
> Students demonstrate an understanding of their responsibility to society as technology creators by evaluating the implications of their work. Students investigate the applications of their work to specific problems or issues.

Knowledge can change the world. As such, the tools of data science come with great responsibility. Data is one way to investigate truth, but only if we also investigate our biases.

| Learning Claim                                                                            	| Possible Forms of Evidence                                                                                                                                                                                                                                                              	|
|-------------------------------------------------------------------------------------------	|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| I can perform research with an audience in mind.                                          	| <ul><li>identification of an audience for the project</li><li>developments of your analysis made with the audience in mind</li><li>responses to your research communication that show that your audience cares about the question</li></ul>                                             	|
| I understand that data analysis can impact understanding and decision-making in the world 	| <ul><li>discussion of the underlying benefits of your quantitative analysis</li><li>discussion of how your research fits into a larger context</li><li>a call to action for how the answers to your question should impact decision making at the community or personal level</li></ul> 	|
| I can identify limitations and potential improvements of my research                      	| <ul><li>discussion of the limitations of your quantitative analysis</li><li>possible approaches to addressing the limitations</li><li>identification of biases present in your analysis</li><li>an outline of future steps for research in your area</li></ul>                          	|
