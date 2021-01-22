---
Title: Networking Project
---

# Unit 00 Networking Project

In this project, you will write a server that provides a service to users of our messaging platform 
(like a bot on Discord). You can do anything for your service – sending Pokemon stats to users,
translating messages, finding weather forecasts – the sky is the limit for what your bot could do.
However, focus on getting a bot that provides a simple service working first, and then scale up to
include more complicated services.

{{< figure src="images/courses/cs10/unit00/00_project_model.png" width="100%" >}}

## Starter Code

{{< code-action >}} Starter code for the project is provided in the
`project-networking` repo. Download it *onto your laptop*.

```shell
$ cd cs10/unit_00
$ git clone https://github.com/the-isf-academy/project-networking-YOUR-GITHUB-USERNAME.git
```

## Planning Document

This is a big project, and you will get lost or frustrated if you don't do some planning up front.
Before you start working on your project, you are required to write a project proposal and get it
approved by a teacher. *You can find your planning doc in your Google Drive folder called "cs10 -
Unit 00 Networking Project: Planning Document".*

Once you have completed the above, meet with a teacher to talk through your plan. Don't start
programming until you get your plan approved, or you might have to change it.

### Bot Service Descriptions
Once you've decided on the service your bot will provide, [add a description in this Google Doc](https://docs.google.com/spreadsheets/d/1DTCPJaFA8SsqSLQgEy-R7UFJyRFKMDPC06ki_Yfa3Ko/edit#gid=1438739874).

This will help other students who may want to use your bot's service.

## Deliverables 

- A planning document in your Google Drive folder 
- A `bot_server` directory in your project repository containing the following files:
    - `server.py` - a Flask server that provides bot services with an API that is directly accessible via HTTP requests by the
    messaging platform through the `/message` route AND by other bots through routes for each of your services.
    for the services your bot provides.
    - `services.py` - a module that defines the services of your bot with a `services_dict` and the functions for each service.
    **At least one service should rely on an external API like another bot or a service you find online.**
    - `README.md` -  documentation for how to use your bot, specifically outline the functionality and parameters of each service.
    - `assessment.md` - a self-assessment of your final project. 
- At least 5 substantial Git commit messages, each explaining what you've changed and why.

**You can find more documentation about what each of the files should contain within the README.md file in the
`bot_server` directory.**

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
