---
title: "3. Graph Algorithms"
type: lab
draft: true
---

# Graph Algorithms

In this lab, you will explore algorithms used for searching through graphs. By the end of the lab,
you will know two different approaches to searching through graphs and the pros and cons of each.

{{< aside >}}
You may be wondering, what's an algorithm anyways?

**Algorithms are just processes that solve problems.** For example, you might have a algorithm
for finding old photos in your photo library. That process might look like this:
- start by scrolling back to around the time you think the photo was taken
- look at a photo
- if the photo you see seems older than the photo you are looking for, scroll down
- if the photo you see seems newer than the photo you are looking for, scroll up
- repeat until you find the photo you are looking for

Like any good problem solving tool, **this process can be used regardless of what photo you are
looking and regardless of what your photo library is like.** It could contain many photos or
just a few. As long as the photos are sorted by the time they were taken, the process will
work.

This process is actually very similar to a searching algorithm used throughout computer
science called **binary search**.
{{< /aside >}}

## A. Graphs
One common way of representing networks is with graphs. You are probably familiar with graphs in math as planes
where you can plot points, lines, and other functions. In computer science, a graph is a data structure consisting
of nodes (known as *vertices*) and the connections between them (known as *edges*).

{{< columns >}}
{{< figure src="images/courses/cs10/unit00/00_algorithms_mathgraph.png" width="100%" title="A graph in math." >}}

<--->

{{< figure src="images/courses/cs10/unit00/00_algorithms_exgraph.png" width="100%" title="A graph in computer science." >}}
{{< /columns >}}

Graphs are used to hold data in many different contexts.

{{< columns >}}
{{< figure src="images/courses/cs10/unit00/00_algorithms_map.png" width="100%" title="Maps can be represented as graphs..." >}}

<--->

{{< figure src="images/courses/cs10/unit00/00_algorithms_social.png" width="100%" title="... and so can social networks." >}}
{{< /columns >}}

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

In code, this would normally be represented without the headers in the table like this:

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
network. Instead, all of devices contribute equally to the network. That way if one device goes down, the network can 
reconfigure itself and continue functioning. Networks like this are useful for distributed tasks like local communication,
distributed processing of large tasks, and sensing and responding to changes in environmental factors across a space.

To set your Pi to mesh network mode, ssh into your Pi and run the following command:

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

But how does the Pi know how to find another Pi in the network when the network is constantly changing and
could be in any configuration with any number of devices?

Enter graph search algorithms.

## B. Graph Search Algorithms
Search algorithms help us find specific elements of large datasets. Applied to graphs, they can help us find paths
between different vertices in the graph.

In this lab, we will explore two search algorithms, Depth-First Search (DFS) and Breadth-First Search (BFS).

{{< youtube id="62IcXF_OF3k" >}}

### Try it out!
{{< code-action >}} Try out DFS and BFS on graphs that you make yourself using [this interactive simulation](https://graphonline.ru/en/).

**Note: When connecting vertices, use unweighted, undirected edges for the purposes of this lab.** If you want to explore
more, you can see what happens when you start addingh weight and direction.

{{< aside >}}
There are actually many more search algorithms than the two presented here. These are actually two of the most
basic algorithms. As you learn more about graphs, you'll discover that the problem of search through a graph can
become quite complicated. For example, what if some of the edges in your graph are longer than others and take more
time to traverse? How do you incorporate this into your search? What if some of the edges in your graph only go in one
direction? Can you still reach every element of the graph?

If you are curious about these questions, great! These questions are at the core of the theory that computer science
is built from. You can research more about algorithms and take computer science classes in university.
{{< /aside >}}

## C. Analyzing search algorithms
BFS and DFS will always be able to find every node in a graph, but that
doesn't mean they are the same. Because of the differences in the algorithms, BFS and DFS perform differently in under
different conditions.

### C.0 X

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

1. Which nodes does DFS find faster than BFS?
1. Which nodes does BFS find faster than DFS?

### C.1 Harder, faster, better, stronger

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

### C.2 You take the high road, and I'll take the low road
Our two different search algorithms sometimes return different paths between vertices. Sometimes this doesn't matter,
but sometimes it can make a big difference. For example:

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
1. What is different about the path from vertex `0` to vertex `7` generated by DFS and the one generated by BFS?
2. What about the algorithms of DFS and BFS cause this difference?
3. Can you find an example graph and search where BFS generates a longer path than DFS?

### C.3 Comparing DFS and BFS
{{< write-action >}} Now that you've got some experience using DFS and BFS, fill out the chart in your lab worksheet
comparing the two different search algorithms we covered in this lab.

Throughout the lab, we've make a big assumption: that DFS and BFS work.

{{< write-action >}} To finish the lab, answer the following question in your lab worksheet: **How can you be sure that
DFS and BFS will always find a path between two vertices in a graph if such a path exists?**


## Deliverables
To submit this lab, make sure you've finalized the Algorithms Lab worksheet in your Google Drive.

