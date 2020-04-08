---
title: CS9
type: course
---

# Welcome to CS 9

## Curriculum

This is a high-level overview of the curricular units that comprise this introductory course.

{{< expand "Unit 0: Drawing" >}}

### Unit 0: Drawing

Working within the context of drawing, students practice building up complex programs from simple ones. We’ll use Python’s turtle library, and use our exported SVGs to cut things on the laser cutter/cnc. Loosely inspired by Chris Proctor’s Python drawing unit from GMS <!--- link broken as of Apr 7, 2020 --->. Programming: Imperative programming; Basics of syntax; functions; decomposition and code reuse. Introductory debugging strategies.

#### Problem sets

Assign students to create various drawing primitives, and use them to build up more complex functions. Note: Require all primitives end with the turtle in the same state as when it started. This makes building up more complex routines much easier.

#### Lab

Practice using pseudocode to plan algorithms. Use this method to write pseudocode (and then code) to generate complex puzzle pictures such as geometric designs, tessellations, and procedurally-generated patterns from nature.

#### Project

Create some personally-meaningful drawing. First, a draft will be due with a sketch of the final project and some planning, including planned subroutines and pseudocode. Use it to make something using the fablab. (eg: engrave your laptop, cut patterns in clothes, mill some useful shape.  

{{< /expand >}}

{{< expand "Unit 1: Data Science" >}}

Programming: Introduction to functional programming; abstraction. Types: int, float, bool. Introduction to data structures. Iterating over lists. Students will build on code reuse from unit 1, this time writing functions without side effects that can be composed. Curriculum: Based on introductory unit from BJC.

#### Problem sets

Write basic functions to perform calculations on numbers and lists. Biggest, smallest, mean, median, mode. Quartiles. Scale, clamp, bin.

#### Labs

Lab 1: Students will write code to plot histograms, scatter plots, and the line of best fit.
Lab 2: Students will be introduced to the basics of Pandas and matplotlib, the standard Python libraries for data analysis and plotting.
<!--- need to update --->

#### Project

Collect some data or use an existing dataset. Frame a research question and use the data to answer it.
<!--- need to update --->
{{< /expand >}}

{{< expand "Unit 2: Games" >}}
### Unit 2: Games

Games and other interactive media are some of the most important texts of the digital age. We will play and discuss several games, discussing how they work technically and drawing on theoretical perspectives to talk about how they create meaningful experiences for the player. Programming: prototyping, decomposition of larger problems, incremental & iterative development of larger projects.

#### Problem sets

Learning how games work can be a great spur toward imagining new ones. This unit’s problem sets will be focused on implementing simple game mechanics.

#### Labs

Lab 1: Using the Arcade platformer tutorial, program a maze game.
Lab 2: Write an algorithm to procedurally-generate random mazes to initialize the maze game.
There will also be ad-hoc mini-labs based on what students need for their games. Likely candidates are gravity, inventories, simulating perspective, animation techniques.

#### Project

Create a game that matters, perhaps as part of a group. This will be very open-ended, but students will be required to submit a substantial proposal, including a game concept with some evidence of prototyping and iteration; wireframes of the game interface; decomposition of tasks and who plans to work on what.  

{{< /expand >}}
{{< expand "Unit 3: Networking" >}}

Perhaps even more than through computational power, computers have transformed our lives through networking. This unit explores how computers interact with each other and will give us opportunities to think about the behavior of larger systems, including how our lives are touched by computer networks. Note: I heard Krates has some neat ideas for teaching networking. I’d love to integrate these ideas (and any others), potentially replacing we should talk! Data structures, error handling. Documentation. Abstraction through layers.

#### Problem sets

Problem sets will focus on asynchronous programming, interacting with JSON, using Python’s requests and Flask libraries.

#### Labs

Lab 1: HTTP requests and responses. Students will learn about the basics of the HTTP protocol (status codes and methods), and data serialization via JSON.
Lab 2: TCP/IP simulation. We will enact a real-world TCP/IP Simulation, discuss network security, hacking, and surveillance, and then groups will write a distributed message-passing client based on the same algorithm.

#### Project

Chatbot microservices. Each student will write an app which responds to network requests. Some examples might be a Chatbot trying to pass the Turing test, a text-based game, or some useful app. A simple web front-end, CLI, and perhaps a configurable Android app will be provided for consuming microservices. We could also consider providing interfaces for email, SMS, or Twitter. It would be powerful to expose the same API for connecting a chatbot microservice to any of these, to emphasize the value of interchangable parts. One limitation is that students will not yet have experience with databases. Students can maintain state with global objects in memory, and will be provided with routines to persist state using pickle or csv (which they will have learned in Unit 2).

Libraries will be provided for:
Sentiment analysis
NLP (eg getting the main noun phrase)
External APIs such as weather, news, etc.
Additionally, students will be encouraged to write, publish, and compose simpler microservices.  

{{< /expand >}}
