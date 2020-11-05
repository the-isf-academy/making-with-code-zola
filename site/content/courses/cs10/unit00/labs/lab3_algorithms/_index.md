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
One common way of representing networks is with graphs. You are probably familiar with graphs in math as planes where you can plot
points, lines, and other functions. In computer science, a graph is a data structure consisting of nodes (known as *vertices*)
and the connections between them (known as *edges*).

{{< figure src="images/courses/cs10/unit00/00_algorithms_exgraph.png" width="100%" title="A graph in computer science." >}}

Graphs are used to hold data in many different contexts.

{{< figure src="images/courses/cs10/unit00/00_algorithms_map.png" width="100%" title="Maps can be represented as graphs..." >}}

{{< figure src="images/courses/cs10/unit00/00_algorithms_social.png" width="100%" title="... and so can social networks." >}}

Importantly, graphs are just representations of the connections between points of data. The spatial layout of the graph doesn't
matter. Actually, graphs are usually represented without a spatial layout at all. One common way to represent graphs is with a
matrix where each row and column represents one vertex in the graph. If there is a 1 where a row and column meet, those vertices
are connected by an edge. IF there is a zero, there is not an edge between those vertices. Here's an example using the MTR:

|                | ... | SYP | Sheung Wan | Central | Admiralty | TST | Wan Chai | Ocean Park | Jordan | ... |
|----------------|-----|-----|------------|---------|-----------|-----|----------|------------|--------|-----|
| ...            |     |     |            |         |           |     |          |            |        |     |
| **SYP**        |     | 1   | 1          | 0       | 0         | 0   | 0        | 0          | 0      |     |
| **Sheung Wan** |     | 1   | 1          | 1       | 0         | 0   | 0        | 0          | 0      |     |
| **Central**    |     | 0   | 1          | 1       | 1         | 0   | 0        | 0          | 0      |     |
| **Admiralty**  |     | 0   | 0          | 1       | 1         | 1   | 1        | 1          | 0      |     |
| **TST**        |     | 0   | 0          | 0       | 1         | 1   | 0        | 0          | 1      |     |
| **Wan Chai**   |     | 0   | 0          | 0       | 1         | 0   | 1        | 0          | 0      |     |
| **Ocean Park** |     | 0   | 0          | 0       | 1         | 0   | 0        | 0          | 0      |     |
| **Jordan**     |     | 0   | 0          | 0       | 0         | 1   | 0        | 0          | 0      |     |
| ...            |     |     |            |         |           |     |          |            |        |     |

In code, this would noramally be represented without the headers in the table like this:

```python
mtr = [ ..., 
        [1, 1, 0, 0, 0, 0, 0, 0],
	    [1, 1, 1, 0, 0, 0, 0, 0],
	    [0, 1, 1, 1, 0, 0, 0, 0],
	    [0, 0, 1, 1, 1, 1, 1, 0],
	    [0, 0, 0, 1, 1, 0, 0, 1],
	    [0, 0, 0, 1, 0, 1, 0, 0], 
	    [0, 0, 0, 1, 0, 0, 0, 0],
	    [0, 0, 0, 0, 1, 0, 0, 0],
	    ...
      ]
```

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

Enter graph search algorithms.

## B. Graph Search Algorithms
Search algorithms help us find specific elements of large datasets. Applied to graphs, they can help us find paths
between different vertices in the graph.

In this lab, we will explore two search algorithms, Depth-First Search (DFS) and Breadth-First Search (BFS).

{{< youtube id="62IcXF_OF3k" >}}

### Try it out!
{{< code-action >}} Try out DFS and BFS on graphs that you make yourself using [this interactive simulation](https://graphonline.ru/en/).

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
BFS and DFS will always be able to find every node in a graph, but that
doesn't mean they are the same. Because of the differences in the algorithms, BFS and DFS perform differently in under
different conditions.

### Harder, faster, better, stronger

Take this graph for example:
{{< figure src="images/courses/cs10/unit00/00_algorithms_graph0.png" width="50%" title="Graph 0: X." >}}

Which algorithm do you think will be best at finding a vertex in this graph starting at vertex `A`?
Are there some vertices that will be easier to find?

{{< code-action >}} Generate this graph in the [simulator](https://graphonline.ru/en/) using the following adjacency matrix
and try using BFS and DFS to search the graph starting at vertex `0`:

```
0, 1, 0, 0, 1, 0, 0, 1, 0, 0, 1, 0, 0,
1, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
0, 1, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0,
0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0,
0, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 0,
0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0,
1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0,
0, 0, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 0,
0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0,
1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0,
0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 1,
0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0,
```

{{< write-action >}} Answer the following questions on your lab worksheet:

1. Which nodes does DFS find faster that BFS?
1. Which nodes does BFS find faster than DFS?


Now it's your turn.

{{< code-action >}} Design a graph (with a start and end point) where DFS performs better than BFS. *Put the adjacency
matrix representation of your graph on your worksheet and indicate the start and stop vertices.*

{{< code-action >}} Design a graph (with a start and end point) where BFS performs better than DFS. *Put the adjacency
matrix representation of your graph on your worksheet and indicate the start and stop vertices.*

{{< write-action >}} Answer the following qustions on your worksheet:
1. With reference to the graphs you created, what general qualities of a search
(the graph and start/stop vertices) make DFS more efficient than BFS?
1. With reference to the graphs you created, what general qualities of a search
(the graph and start/stop vertices) make BFS more efficient than DFS?
1. For the graphs you created, imagine that a random vertex will be chosen as the end point for a search.
Will one algorithm be a better choice than the other if you don't know where the end point will be before you choose?

### You take the high road, and I'll take the low road
Our two different search algorithms sometimes return different paths between vertices. Sometimes this doesn't matter,
but sometimes it can make a big differnce. For example:

{{< figure src="images/courses/cs10/unit00/00_algorithms_graph1.png" width="50%" title="Graph 1: Loop." >}}

{{< code-action >}} Generate this graph in the [simulator](https://graphonline.ru/en/) using the following adjacency matrix
and try using BFS and DFS to search the graph starting at vertex `0`:

```
0, 1, 0, 0, 0, 0, 1, 0,
1, 0, 1, 0, 0, 0, 0, 0,
0, 1, 0, 1, 0, 0, 0, 0,
0, 0, 1, 0, 1, 0, 0, 0,
0, 0, 0, 1, 0, 1, 0, 0,
0, 0, 0, 0, 1, 0, 1, 0,
1, 0, 0, 0, 0, 1, 0, 1,
0, 0, 0, 0, 0, 0, 1, 0,
```

{{< write-action >}} Answer the following questions in your lab worksheet:
1. What is different between the path from vertex `0` to vertex `7` generated by DFS and the one generated by BFS?
2. What about the algorithms of DFS and BFS cause this difference?
3. Can you find an example graph and search where DFS generates a longer path than BFS?

### Comparing DFS and BFS
{{< write-action >}} To wrap up the lab, fill out the chart in your lab worksheet comparing the two different
search algorithms we covered in this lab, DFS and BFS.

## Deliverables
To submit this lab, make sure you've finalized the Algorithms Lab worksheet in your Google Drive.

