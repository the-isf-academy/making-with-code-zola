---
title: Teaching notes
type: notes
---

## Course structures

### Projects

One primary structure in the course will be open-ended projects. The initial units will provide scaffolding, supporting students in designing and implementing projects. Later in the year, students will design their own projects independently.

### Labs

Students will work on labs in class which integrate the skills and emphasize developing collaborative problem-solving. Early in the year, labs and projects will be tightly-integrated; students will be guided through creating projects. One feature of labs is that we will be providing some of the libraries students use, allowing them to interact with broader computational systems than they would be able to do on their own. For example, students will initially encounter machine library through functions we provide which allow them to do powerful things with their code.  

### Problem Sets

There will be regularly-assigned problem sets supporting students in practicing their skills. (We should assess school culture, but I like the idea of having a small problem set due in each day of class). Students may work together on these, but they must be coded independently. Problem sets will be assessed automatically so that students get immediate feedback. Generally, problem sets will lag behind labs so that they are practice with content we’ve already explored together.

### Infrastructure

The course will be taught in Python. Each student will do her work primarily in Github repositories. We will use GitHub Classroom to manage assignments. Each project, lab, and problem set will be a separate repo.

### Assessment

Projects and labs will be assessed manually, giving feedback not just on correctness but on style, etc. Problem sets will be graded automatically via GitHub webhooks--every time commits are pushed, the auto-grader will assess the assignment and create or update an Issue giving feedback. We will use pedal to automatically grade problem sets.
<!--- is this still accurate??? --->

## Grading

| Score           | Points | Description                                |
| --------------- | ------ | ------------------------------------------ |
| Full credit     | 3/2    | Completed everything, with flying colors)  |
| Average credit  | 2/2    | Completed everything)                      |
| Subpar          | 1/2    | Not completed or not correctly completed)  |
| No submission   | 0/2    | Or no evidence of good-faith effort        |

Late - deduct 1 point for submissions between 1-7 days late  
We will not accept late submissions after 7 days  
Revised work - If you submit something that you put a good faith effort by the first deadline and you want to revise the homework, we can accept revisions up until the end of the unit.  

When we assess students’ work manually, we will give feedback on the following:

+ **Creativity** of the homework submission
+ **Courage** with code -  willingness to experiment / try new things
+ **Effectiveness** of concepts/tools usage -  Appropriate, effective use of tools and concepts (suggest when there could be a better option)
+ **Coding style**
    + Descriptive function and variable naming
    + Documenting the functionality of functions with comments
    + Decomposition of programs into functions
    + Efficiency and elegance of code

<!--- remove reference to 'Chris'? --->
## Norms 

+ **Getting help:** When working on individual projects and on problem sets, students will often need help from teachers. It is important to create structures to allocate teacher time so that pushier students can’t dominate, and to build a culture where it’s a good thing to be stuck, to need help, and to seek help.  
    + One useful tool is the help queue, simply a list on the whiteboard where people can sign up if they need help. All the people sign up at the beginning of class get helped in a random order (to prevent a rush). Respect the queue.
    + Encourage students to seek help from peers. And to look for help online. In particular, it’s not OK to sit idly waiting for help from a teacher.
    + When many students are having the same issue, it may be time to schedule a mini-lesson, 10 or 15 minutes dedicated to working an example to address the issue in a side part of the classroom. All students would be invited (but generally not required to attend). This would generally take priority over helping individuals, since it can help many people at once.
    + When a student is really struggling and needs ongoing support, it can be helpful to break things down into small tasks, help the student get to the point where she can tackle one, and then say, “It looks like you can do this part. Can I go help somebody else and then check back in with you in five minutes?” Make sure you do!
    + Github issues will make it easier to create a practice of identifying problems and asking for help offline. This could be productively combined with office hours. If this turns out to be helpful, it could be nice to occasionally make this work visible in class, for example by starting class off by presenting an interesting bug. (Some students will be much more comfortable asking for this kind of help; when they see that others are doing so, it can help them to also ask for help.)
    + Stanford CS TA’s often had a practice of not looking at students’ code (they wanted to help debug thinking, not code). We believe this is not a helpful stance for supporting beginners.  
+ **Funds of knowledge** refers to the idea that we will look at students as having lots of resources they can deploy in their learning (rather than viewing them in terms of their deficits). This also means we need to let go of the idea that we’re solely in the position of determining what’s worthwhile in CS. Our students are going to create things that are worthwhile and successful on their terms, not ours. We are going to support them, while also being warmly demanding. This is not a radical proposition, especially in CS: It’s such a new field that nobody really knows what CS is or what its boundaries are. If we’re finding ways of working that are effective, thinking about ideas that feel powerful, and making things that feel like they matter, then we’re doing the right thing.  
+ **Assigning competence:** Create practices by which students are seen as experts.  
    + One useful practice that embodies this: when helping people from the queue, follow up helping a student by saying, “It looks like you understand this issue pretty well now. When I see another student having the same problem, may I send them to you for help?” That way, the student solidifies the understanding by teaching someone else, and gets to be an expert at that issue. You can then keep directing students to that expert for days.  
+ **Authorship:** It is very important that each student develop as an author of her code.  
    + Never touch a student’s keyboard. Instead, sit with the student and guide her in what to do. It can be helpful to bring another laptop, increase the font size, and type out code for the student to copy. It’s also great to have portable whiteboards or writable desk surfaces, so you can develop pseudocode together that then stays with the student. (The only exception would be if there is some error at a deeper level than the student would be expected to know about, eg incompatible package versions installed.)  
    + For problem sets, students should never look at each others’ code. They may work on problems together, using pseudocode and diagrams. This is going to be a challenge, because pair programming might be very productive during labs and group projects.  
+ **Groupwork:** Small groups are an important context for high-quality disciplinary talk. When students get to choose their groups, they can take advantage of existing social relationships. However, this can create in equities (the strongest students cluster together) and can also bring social tensions into the classroom.
    + Our recommendation is to always assign seats and groups, change groups regularly (perhaps every unit), and allow students some private input (eg “I really don’t get along with X”).


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

## Background reading

Need to develop this section
