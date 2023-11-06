# EECS 330 Lab-9 (Advanced Graph Algorithms)


## Goal: Implementation of Advanced Graph Algorithms.

### Due date (based on your lab time):
- Monday 11/06/2023
  - Due on Thursday 10/09/2023 11:59 pm
- Tuesday 11/07/2023
  - Due on Friday 11/10/2023 11:59 pm
- Wednesday 11/08/2023
  - Due on Saturday 11/11/2023 11:59 pm
- Friday 11/10/2023
  - Due on Monday 10/13/2023 11:59 pm

In this lab, we are going to learn some advanced graph algorithms.

### A. Implement Dijkstra's Shortest Path Tree Algorithm.

Dijkstra's algorithm is one of the important graph algorithms. It is used to find the shortest path from the root node
to other nodes in weighted or directed graph. Priority queue or heap is a data structure, that is primarily used to design
such algorithm.

```Python
class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for _ in range(vertices)] for _ in range(vertices)]

    def add_edge(self, u, v, w):
        self.graph[u][v] = w
        self.graph[v][u] = w

    def dijkstra(self, src):
        # Stores shortest distance.
        dist = [sys.maxsize] * self.V
        # Shortest distance to the same node is 0.
        dist[src] = 0
        
        # Your code.
        
        # You have to call print_solution by passing dist.
        # In this way everyone's output would be standardized.
        self.print_dijkstra(dist)

    def print_dijkstra(self, dist):
        print("Vertex \t Distance from Source")
        for node in range(self.V):
            print(f"{node} \t->\t {dist[node]}")
```

### B. Implement Prim's Minimum Spanning Tree.

Prim's algorithm another graph algorithm, that is used to find [Minimum Spanning Tree](https://algs4.cs.princeton.edu/43mst/)
of connected and unidirectional graph. Minimum Spanning Tree is a subgraph or subset of connected or unidirectional graph
that connects all the vertices together, with no cycles, and while the total edge weight minimal. Priority queue or min-heap
datastructure is typically used to implement Prim's algorithm. Complexity of `O(E + V log V)` can be achieved using an
efficient implementation. Where, E is number of edges and V is number of vertices.

```Python
class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for _ in range(vertices)] for _ in range(vertices)]

    def add_edge(self, u, v, w):
        self.graph[u][v] = w
        self.graph[v][u] = w

    def prim(self):
        # Store the resulting graph.
        # where result[i] keeps the source vertex.
        # See the example output for expected result.
        result = [None] * self.V
        
        # Your code.
        
        # You have to call print_solution by passing the output graph.
        # In this way everyone's output would be standardized.
        self.print_prim(result)

    def print_prim(self, result):
        print("Edge \t Weight")
        for i in range(1, self.V):
            print(f"{result[i]} - {i} \t {self.graph[i][result[i]]}")
```

For e.g. For the following graph:

```Python

# Create a graph with 21 vertices.
graph = Graph(9)

# Add edges and their weights.
graph.add_edge(0, 1, 4)
graph.add_edge(1, 2, 8)
graph.add_edge(2, 3, 7)
graph.add_edge(3, 4, 9)
graph.add_edge(4, 5, 10)
graph.add_edge(5, 6, 2)
graph.add_edge(6, 7, 1)
graph.add_edge(7, 0, 8)
graph.add_edge(7, 1, 11)
graph.add_edge(7, 8, 7)
graph.add_edge(8, 2, 2)
graph.add_edge(6, 8, 6)
graph.add_edge(5, 2, 4)
graph.add_edge(5, 3, 14)

# The output should look like:

0 -> 1 	 4
1 -> 2 	 8
2 -> 3 	 7
3 -> 4 	 9
2 -> 5 	 4
5 -> 6 	 2
6 -> 7 	 1
2 -> 8 	 2
```


### C. Kruskal's Minimum Spanning Tree.

Kruskal's Minimum Spanning Tree is another way to find [Minimum Spanning Tree](https://algs4.cs.princeton.edu/43mst/)
of connected and unidirectional graph. Kruskal's algorithm uses greedy approach unlike Prim's algorithm, that uses incremental
approach. Disjoint set datastructure (that you have previously learned) is used to implement Kruskal's algorithm. Complexity
of `O(E log E)` can be achieved using an efficient implementation.

```Python
class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for _ in range(vertices)] for _ in range(vertices)]

    def add_edge(self, u, v, w):
        self.graph[u][v] = w
        self.graph[v][u] = w

    def kruskal_mst(self):
        # Your code.
        
        # Similar to the previous e.g. print your
        # resulting graph.
        print_kruskal(result)

    def print_kruskal(self, result):
        print("Edge \t Weight")
        # Note that the below code is slightly different than the Prim's.
        # You can change this print code according to your choice, but
        # you have to display your graph in (vertex->vertex weight) format.
        for edge in result:
            print(f"{edge[0]} -> {edge[1]} \t {edge[2]}")
```

### D. Testing.

```Python
# Create a graph with 21 vertices.
graph = Graph(21)

# Add edges and their weights.
graph.add_edge(0, 1, 4)
graph.add_edge(0, 2, 1)
graph.add_edge(1, 3, 3)
graph.add_edge(2, 4, 2)
graph.add_edge(3, 5, 2)
graph.add_edge(4, 6, 2)
graph.add_edge(5, 7, 2)
graph.add_edge(7, 8, 2)
graph.add_edge(6, 8, 2)

graph.add_edge(8, 9, 5)
graph.add_edge(8, 10, 4)
graph.add_edge(9, 11, 3)
graph.add_edge(10, 11, 1)

graph.add_edge(11, 12, 1)
graph.add_edge(12, 13, 1)
graph.add_edge(13, 14, 1)

graph.add_edge(14, 15, 1)
graph.add_edge(14, 16, 10)
graph.add_edge(15, 17, 1)
graph.add_edge(16, 20, 1)
graph.add_edge(17, 18, 1)
graph.add_edge(18, 19, 1)
graph.add_edge(19, 20, 1)

# Run Dijkstra's algorithm from source vertex 0.
graph.dijkstra(0)

# Find and print the Prim's Minimum Spanning Tree (MST).
graph.prim()

# Find and print the Kruskal's Minimum Spanning Tree (MST).
graph.kruskal()

```

Testing and Grading: You should submit your code via a GitHub repository created for EECS 330. For this lab, create a dir named "Lab-9" and push all your .py files into that dir on the GitHub repository to complete your lab work.

Submission and Deadline: Please submit through GitHub and grades will be posted based on completed work without any issues.