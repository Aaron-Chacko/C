# Prim's Minimum Spanning Tree

## Overview

Prim's Minimum Spanning Tree (MST) algorithm is a fundamental graph algorithm used in computer science and network design. The main goal of Prim's algorithm is to find the subset of edges in a weighted, undirected graph that connects all vertices without forming any cycles and with the minimum possible total edge weight.

## Features

- **Greedy Approach**: Prim's algorithm follows a greedy strategy, which means it makes a series of choices, each of which looks best at the moment, with the hope that these choices will lead to an optimal solution. It always chooses the edge with the smallest weight that expands the growing spanning tree.

- **Connectivity**: The algorithm starts from an arbitrary vertex and grows the MST one edge at a time, ensuring that the graph remains connected at all stages.

- **Performance**: Prim's algorithm is particularly efficient for dense graphs, where the number of edges is much larger than the number of vertices. It has a time complexity of O(E log V) when implemented with a priority queue, where E is the number of edges and V is the number of vertices.

## Prerequisites

- A C compiler (e.g., GCC) installed on your system.
- Basic knowledge of how to compile and run C programs.

### Algorithm

1. Initialize a key value for all vertices as infinite and set the key of the first vertex as 0.
2. Set the parent of the first vertex as -1 (it will be the root of the MST).
3. Repeat until all vertices are included in the MST:
   - Pick the vertex with the minimum key value that is not yet included in the MST.
   - Include the picked vertex in the MST.
   - Update the key values and parent indices of the adjacent vertices of the picked vertex.
4. Print the edges and weights of the MST.

### Example Input

The input graph is defined in the code as an adjacency matrix:

```c
int graph[V][V] = {
    {0, 2, 0, 6, 0},
    {2, 0, 3, 8, 5},
    {0, 3, 0, 0, 7},
    {6, 8, 0, 0, 9},
    {0, 5, 7, 9, 0}
};
```

### Example Output
```c
Edge   Weight
0 - 1  2
1 - 2  3
0 - 3  6
1 - 4  5
```

## Complexity

- **Time Complexity**: \(O(V^2)\)
- **Space Complexity**: \(O(V^2)\)

## Limitations

1. **Graph Representation**: Prim's algorithm is more efficient for dense graphs. For sparse graphs, Kruskal's algorithm may be preferable.

2. **Non-Negative Weights**: The algorithm requires all edge weights to be non-negative; it cannot handle negative weights effectively.

3. **Single-Source**: It only finds the MST for the connected component containing the starting vertex, ignoring any other disconnected components.

4. **Dynamic Changes**: Prim's algorithm is not efficient for graphs that frequently change, as it must be recomputed from scratch.

5. **Scalability**: The \(O(V^2)\) time complexity may become a bottleneck for very large graphs, necessitating more scalable alternatives.

