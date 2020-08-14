---
title: "Unit 00: Networking"
type: unit
---

## Labs

- Setting up Raspberry Pis, networking basics. SSH into Pi. Pinging IP addresses.
- HTTP requests and responses to send and recieve environmental information from a
central server. Students will learn about the basics of the HTTP  protocol (status
codes and methods), and data serialization via JSON.
- TCP/IP simulation. We will enact a real-world TCP/IP Simulation, discuss network
security, hacking, and surveillance, and then groups will write a distributed
message-passing client based on the same algorithm.
- Cyclic graph detection. After the cyclic graph problem set, students will
  discuss their algorithms, and then decide on one to implement. They will
  implement a function which takes a graph input (dot format) and the function
  will either identify a cycle or determine that there is no cycle. 

## Homework

- Practice with dictionaries (extracting data from JSON when provided a schema)
- Practice with HTTP responses and requests.

## Problem set

- Intro to logic/proofs
  - Students will learn the basics of logic beginning with sets. This will include
  set operations (intersection, union, difference), set building (filters and 
  transformations), set relations (equality, subsets, supersets), and set cardinality.
  - Students will then use the basics of set theory to explore mathematical proof
  including direct proofs with cases, lemmas, and vacuous truths and indirect proofs
  by contradiction and contrapositive. Proofs will explore parity, set relations, and
  visual/geometric proofs.
  - Resources
    - [Mathematical Foundations of Computing Course Reader](web.stanford.edu/class/cs103/handouts/Mathematical%20Foundations%20of%20Computing.pdf)
    - [Mathematical Foundations of Computing Sets and Proofs Problem Set](http://web.stanford.edu/class/cs103//assnFiles/pset1/Problem%20Set%201.pdf)
- Building off of our TCP/IP simulation, imagine much larger networks of people. 
  - We can represent networks as trees. Draw a couple. 
  - Math with trees. If you have a network with depth D and each node can have N
    children, how many nodes are supported?
  - Provide a simulation of a traversable tree and have students practice 
    breadth-first search and depth-first search. Then write out the algorithm
    precisely. 
  - Provide an example of a proof by negation that breadth-first search will
    find any node in the network. Then ask students to write a similar proof for
    depth-first search. 
- Cyclic and acyclic graphs. If we are going to write microservices, they might
  depend on other microservices. 
  - Draw out a dependency tree for a given scenario. 
  - If there is a cycle in the dependency tree, we have a problem. Write out an
    algorithm for checking to make sure there is no cycle.

## Project

Microservices. Each student will write an app which responds to network requests.
Some examples might be a Chatbot trying to pass the Turing test, a text-based game,
or some useful app. Students will deploy their microservices to their Raspberry Pis
which will be networked via a VPN, so that even if we are remote teaching, services
can be consumed from each student's house.

A simple web front-end, and CLI will be provided for consuming microservices. We could
also consider providing interfaces for email, SMS, or Twitter. It would be powerful to
expose the same API for connecting a chatbot microservice to any of these, to emphasize
the value of interchangable parts. One limitation is that students will not yet have
experience with databases. Students can maintain state with global objects in memory, and
will be provided with routines to persist state using pickle or csv (which they will have learned in Unit 2).

Libraries will be provided for:
- Sentiment analysis
- NLP (eg getting the main noun phrase)
- External APIs such as weather, news, etc.
- Additionally, students will be encouraged to write, publish, and compose simpler microservices.  

