---
title: "3. Graph Algorithms"
type: lab
draft: false
---

# Graph Algorithms

In this lab, you will explore algorithms used for searching through graphs. By the end of the lab, you will
know two different approaches to searching through graphs and the pros and cons of each.

{{< aside >}}
You may be wondering, what's an algorithm anyways?

Oxford Languages defines an algorithm as

> *a process or set of rules to be followed in calculations or other problem-solving operations, especially by a computer.*

So, in this lab you will be learning about a process that you can apply to any graph that will show you a path between two
in the graph.
{{< /aside >}}

## A. Graphs
One common way of representing networks is with graphs. In computer science, a graph is a data structure
consisting of nodes (known as *vertices*) and the connections between them (known as *edges*).

{{< figure src="images/courses/cs10/unit00/00_algorithms_graph.png" width="100%" title="A graph in computer science." >}}

Graphs are used to hold data in many different contexts.

{{< figure src="images/courses/cs10/unit00/00_algorithms_map.png" width="100%" title="Maps can be represented as graphs..." >}}

{{< figure src="images/courses/cs10/unit00/00_algorithms_social.png" width="100%" title="... and so can social networks." >}}

Graphs are useful in the context of networking because the global internet can be represented as a big graph. In this
case, internet connected devices like servers and your computer are vertices while the cables that connect them are edges.

### Mesh Networks
We can model the internet at large at a smaller scale by using our Raspberry Pis to create a mesh network. A mesh network
is a network of devices that connect to each other by propogating messages along the network. No one device controls the
netwrok. Instead, all of devices contribute equally to the network. That way if one device goes down, the network can 
reconfigure itself and continue functioning. Networks like this are useful for distributed tasks like local communication,
distributed processing of large tasks, and sensing and responding to changes in environmental factors across a space.

To set your Pi to mech network mode, ssh into your Pi and run the following command:

```shell
$ sudo setup-mesh-network
```

Your Pi will now join the class mesh network and begin communicating with other Pis. This means
you will get booted off the SSH connection since it was happening over the network your computer was connected to.

By operating one of the Pis directely using a keyboard and display, you can see how the Pis are connected.

The following command shows all of the Pis that are one edge away from your Pi (these vertices are known as *neighbors*):

```shell
sudo batctl n
```

The following command will show you the entire network of Pis in the mesh network as a graph:

```shell
sudo batadv-vis
```

Finally, you can see the paths through a network that the Pis use to communicate to each other. For example
if you wanted to know how your Pi communicated with raspberrypi-14:

```shell
sudo batctl traceroute raspberrypi-14
```

You may notice that the route is always the shortest path between the two Pis. This allows the network
to operate efficiently without having unnecessary hops between nodes in the network.

But how does the Pi know how to find another Pi in the network when the network is constantly change and
could be in any configuration with any number of devices?

Enter graph search algoriths.

## B. Graph Search Algorithms
Search algorithms help us find specific elements of large datasets. Applied to graphs, they can help us find paths
between different vertices in the graph.

In this lab, we will explore two search algorithms, Depth-First Search (DFS) and Breadth-First Search (BFS).

### Depth first search

### Breadth first search

{{< aside >}}
There are actually many more search algorithms than the two presented here. These are actually two of the most
basic algorithms. As you learn more about graphs, you'll discover that the problem of search through a graph can
become quite complicated. For example, what if some of the edges in your graph are longer than others and take more
time to traverse? How do you incorporate this into your search? What if some of the edges in your graph only go in one
direction? Can you still reach every element of the graph?

If you are curious about these questions, there is a whole field within computer science dedicated to answering
questions like this.
{{< /aside >}}

## C. Analyzing search algorithms

### Mazes as graphs

### Pros and cons


If you are stuck, try taking on the following perspectives when creating your mazes:

* You are the designer of a database and you want your search to run really qucikly. What maze can you make
where each algorithm performs at its best?
* You have no control over the maze and it is randomly generated. What algorithm works best?
* You are a hacker trying to slow down a piece of software that uses BFS or DFS. What maze can
you make that will cause the algorithm to run really slowly?

## Deliverables
To submit this lab, make sure you've pushed the following files to Github:
- `simple_server.py`
- `server.py`

