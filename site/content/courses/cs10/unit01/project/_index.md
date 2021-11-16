---
Title: Games Project
draft: false
---

# Unit 01 Games Project

In this project, you will create a game and write a terminal interface for it.
You have four options to choose from – Spelling Bee, Word Search, Mastermind, or Rock, Paper, Scissors.
Once you get your game playable, you can then scale it up to
include more complicated interactions like viewing the rules, adding random elements, adding more puzzles, etc.

<!-- {{< figure src="images/courses/cs10/unit00/00_project_model.png" width="100%" >}} -->

## Structure

You can choose one of these four games to implement. You will create your own game class and your own view class, but you will be given pseudocode to help you with the logic of how your game driver will work.

{{< code-action >}} The three empty files that you will implement are provided in the
`project-games` repo. Download it *onto your laptop*.

```shell
$ cd cs10/unit_00
$ git clone https://github.com/the-isf-academy/project-networking-YOUR-GITHUB-USERNAME.git
```

## Planning Document

This is a big project, and you will get lost or frustrated if you don't do some planning up front.
Before you start working on your project, you are required to write a project proposal and get it
approved by a teacher. *You can find your planning doc in your Google Drive folder called "Unit 01 Games Project: Planning Document".*

## Games
Below are the four games that you can choose to implement. Look at the provided pseudocode and try paying each game to help you decide which you'd like to do!

### Spelling Bee

[To play the NTY Spelling Bee, click here](https://www.nytimes.com/puzzles/spelling-bee)

  **SpellingBee Pseudocode**

```
loop
    invalid_letters = False
    user makes a guess
    loop through each letter in the guess
        if the letter isn't one of the allowed letters
          invalid_letters = True
    if invalid_letters == True
        tell the user not to use unallowed letters
    else if the key letter is not in the guess
        tell the user they must include the key letters
    else if the guess is already in the list of guessed words
        tell the user they have already guessed that word
    else if the guess is in the valid word list
        congratulate the user and add the guess to the list of guessed words
    else
        tell the user that the word isn't one of the words on your list
```


### Word Search
[To play Word Search, click here](https://thewordsearch.com/puzzle/183/fruits/)

  **Word Search Pseudocode**

### Mastermind
[To play Mastermind, click here](https://www.webgamesonline.com/mastermind/)

  **Mastermind Pseudocode**
```
loop until the guess limit is reached
    right_place = 0 (how many pins are the right color and right place)
    right_color = 0 (how many pins are the right color but in the wrong place)
    user makes a guess
    if the guess is completely correct
        tell the user good job
    else
        loop 4 times
            if the guess pin is the same as the code pin
                increase right_place by 1
        overlap = set(guess) & set(code)          
        right_color = (len(overlap) - right_place)
        tell the user about right_place and right_color
```

### Rock, Paper, Scissors
[To play Rock, Paper, Scissors click here](https://www.afiniti.com/corporate/rock-paper-scissors)

  **Rock, Paper, Scissors Pseudocode**

## Deliverables

- A planning document in your Google Drive folder
- `run_game.py` - when this file is run, the game should begin in the terminal. It will contain most of the logic of the game
- `view.py` - your View class should handle all the printing to the terminal and user interactions
- `game_object.py` - the class in this file should create the object that stores any necessary data about the game
- `README.md` -  documentation for how to run your game
- `assessment.md` - a self-assessment of your final project
- At least 5 substantial Git commit messages, each explaining what you've changed and why.

**You can find more documentation about what each of the files should contain within the README.md file.**

### Example Bot
Here is a video of what your finished game experience might be like:   __________

## Timeline
### cs10.1
{{< figure src="images/courses/cs10/unit00/00_project_cs10_1.png" width="100%" >}}
### cs10.2
{{< figure src="images/courses/cs10/unit00/00_project_cs10_2.png" width="100%" >}}

## Assessment
You are responsible for assessing your own project, though your teachers will let you know if they
disagree. In `assessment.md`, you are required to explain how your project should be scored, and
to give evidence to support your assessment. The rubric is based on claims that you should be able
to make about your learning in this unit. Each of these claims comes with examples of evidence that
would show that you can make the claim about your learning.

**To do well in this project, you should be able to concretely justify that you have achieved each of
the learning claims.** So, if the rubric says you should be able to understand HTTP communication and
that an example of that is making an HTTP request to an external service, then you should make an HTTP
request in your project and point to it in your self-assessment.
If the rubric says you should be able to thoughtfully plan a large project and that an example of that
is a thorough design document, you should create a detailed design document and discuss in your self-assessment
how this design document helped you create your project.

Here's a guide for using the rubric:
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

> Students appropriately apply computer science concepts and tools in context. On top of computer
> science concepts and tools, students apply computational thinking practices including habits such
> as writing pseudocode, developing iteratively, using abstractions, decomposing problems, and debugging.

In this unit, we explored the way **computers communicate with each other over the internet**. We learned
**how applications make HTTP requests to send and receive information from a server**. You wrote a server
application to **receive, interpret, and respond to HTTP requests**. Finally, we explored the **networks
between computers** that arise when computers need to communicate with each other over long distances.

| Learning Claim                                                                                                | Possible Forms of Evidence                                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I can read documentation to use services written by others.                                                   | <ul><li>Usage of the services of an external API or another student’s bot that helps you provide your services.</ul></li>                                                                                                                                                                                                                                                          |
| I understand HTTP communication between clients and servers.                                                  | <ul><li>Routes defined for each service your bot provides</li> <li>HTTP requests made to another bot or external API with well-formed addresses and payloads/parameters</li> <li>Parsing of HTTP responses to use response data in services</li> <li>Responses to HTTP requests formatted as JSON objects</li> <li>Descriptive error reporting when something goes wrong</li></ul> |
| I effectively use the principles of decomposition and abstraction to make my code more efficient and elegant. | <ul><li>At least one module containing the services your bot provides</li> <li>Services implemented so they can simultaneously be accessed through the message platform AND the bot’s API</li> <li>Parameterized services (your services don’t always return the same thing, but instead respond differently based on inputs)</li></ul>                                            |


### Criterion B: Planning and development
> Students create personally meaningful projects through an iterative design cycle. Students’ work is
> grounded in a development plan which students create before beginning the project. Students document
> the development of their projects in order to create a record of decisions, assumptions, and
> lingering flaws. Students define the intended functionality and develop towards evaluation.

In this unit, you planned a project with a design document, **navigating a reliance on an external
service**. You may have been required to **develop software while waiting for a service you depend
on to be developed.** Additionally, you learned about the importance of **documenting your software
so that it can be effectively used by others.**

| Learning Claim                                                                  | Possible Forms of Evidence                                                                                                                                                                                                                                                                                                 |
|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I can thoughtfully plan a large computer science project.                       | <ul><li>A thorough planning document.</li> <li>Updates to your project plan to account for challenges during development</li></ul>                                                                                                                                                                                         |
| I can iteratively develop a project using version control tools such as GitHub. | <ul><li>At least 5 regular and descriptive git commits on your project</li> <li>A stub function/service you wrote to stand in for a function that had not yet been developed (by you or your classmates)</li> <li>A transition from a basic set of services offered by your bot to a more robust set of services</li></ul> |
| I can document my software so that it is readable and usable by others.         | <ul><li>A description of the services your bot provides in the README.md file</li></ul>                                                                                                                                                                                                                                    |

### Criterion C: Evaluation
> Students produce evidence of a testing plan that evaluates the main areas of functionality of the
> product and reflect on the development process as well as a proposal for further development to
> improve the shortcomings of the current product.

In the unit, you developed software in an environment where the **dependence on other services (either
a client or server) influenced the requirements for your work**. In doing so, you learned to **read and
interpret errors across multiple layers of a software project**. Additionally, you learned to **test
your code, paying particular attention to edge cases**.

| Learning Claim                                                                                                                        | Possible Forms of Evidence                                                                                                                                                                                                                                                  |
|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I can identify different scenarios in which my code may be used and outline the expected functionality of my code in these instances. | <ul><li>A list of general use cases for your bot’s services including the expected functionality of your bot in those cases</li> <li>An identification of the edge cases (erroneous or malicious uses of your software that fall outside of the basic use cases)</li></ul> |
| I can develop a testing strategy to ensure my code works as expected.                                                                 | <ul><li>A list of tests you will run to make sure your code works based on your use cases and responses</li> <li>Changes your made after finishing development and running your tests</li></ul>                                                                            |
