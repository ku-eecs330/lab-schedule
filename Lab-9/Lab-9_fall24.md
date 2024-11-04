# EECS 330 Lab-9


## Goal: Implementation of Graph Traversals and Path Finding

### Due date (based on your lab time):
- Monday 11/04/2024
  - Due on Friday 11/8/2024 11:59 pm
- Tuesday 11/05/2024
  - Due on Saturday 11/9/2024 11:59 pm
- Wednesday 11/06/2024
  - Due on Sunday 11/10/2024 11:59 pm
- Friday 11/08/2024
  - Due on Tuesday 11/12/2024 11:59 pm


### A. Implementation of Graph Path Finding and Analysis.

You are provided with a Graph represented as an adjacency list. The graph is defined using the Graph class with nodes and edges. Your task is to implement the following graph algorithms: 

1. Find the shortest path between two given vertices using both BFS and DFS.
2. Find the number of connected components in a graph (connected or disconnected).
3. Check if the graph is bipartite using BFS or DFS.

```Python
class Graph:
    def __init__(self, vertices):
        self.vertices = vertices
        self.adjacency_list = [[] for _ in range(vertices)]

    def add_edge(self, u, v):
        """Add an edge between vertices u and v."""
        pass
```

**A.1 Shortest path between two given vertices using both BFS and DFS**

Implement the Shortest path between two given vertices Start and End using DFS and BFS. Return list all vertex on the path and distance (no.of edges ) from Start to End. Print "no path" in case there no path between Start and End.

```python
def dfs_shortest_path(self, start, end):->list,int
    """Find the shortest path using BFS from Start to End."""
    pass

def bfs_shortest_path(self, start, end): ->list,int
    """Find the shortest path using BFS from Start to End."""
    pass

```
**A.2 Find the number of connected components in a graph**

Check number of connected components in the given graph. Print count of connected graphs.You can use either DFS or BFS to find the number of connected components in a graph. Both algorithms are suitable for traversing the graph and identifying connected components.
```python
def count_connected_components(self):-> int
    """Find the number of connected components."""
    return num_components
    pass
```

**A.3 Check if given grpah is Bipartite**

In a bipartite graph, the set of vertices can be divided into two disjoint subsets such that no two vertices within the same subset are adjacent (linked). This can be visualized by assigning two different colors to the vertices, ensuring that no two adjacent vertices share the same color.
For disconnected graphs, it's possible to check each connected component individually for bipartiteness. If all connected components of a disconnected graph are bipartite, then the entire graph can be considered bipartite.

Check if the given graph is Bipartite. Please use your BFS implementation to implement this. Your should return True or False

```python
 def is_bipartite(self): ->bool
    """Check if graph is bipartite."""
    pass
```
### Testing logic.

```Python
# Testing logic for the lab assignment

graph = Graph(20)

# Add edges to create a connected component and disconnected ones
graph.add_edge(0, 1)
graph.add_edge(0, 2)
graph.add_edge(1, 3)
graph.add_edge(1, 4)
graph.add_edge(2, 5)
graph.add_edge(2, 6)
graph.add_edge(3, 7)
graph.add_edge(3, 8)
graph.add_edge(4, 9)
graph.add_edge(4, 10)
graph.add_edge(5, 11)
graph.add_edge(5, 12)
graph.add_edge(6, 13)
graph.add_edge(6, 14)
graph.add_edge(7, 15)
graph.add_edge(7, 16)
graph.add_edge(8, 17)
graph.add_edge(8, 18)
graph.add_edge(9, 19)
graph.add_edge(15, 16)  
graph.add_edge(17, 18) 
graph.add_edge(10, 11)
graph.add_edge(11, 19)

### Test Case 1: Shortest Path

bfs_path, bfs_distance = graph.bfs_shortest_path(0, 19)
dfs_path, dfs_distance = graph.dfs_shortest_path(0, 19)

print(f"BFS Shortest Path from 0 to 19: {bfs_path} ")
print(f"BFS Shortest distance from 0 to 19: {bfs_distance}")

print(f"DFS Shortest Path from 0 to 19: {dfs_path}")
print(f"DFS Shortest distance from 0 to 19: {dfs_distance}")

### Test Case 2: Number of Connected Components

num_components = graph.count_connected_components()
print(f"Number of connected components in the graph: {num_components}")

### Test Case 3: Bipartite Check

is_bipartite = graph.is_bipartite()
print(f"Is the large graph bipartite? {'Yes' if is_bipartite else 'No'}")

# Create a graph for simpler testing
graph = Graph(7)
graph.add_edge(0, 1)
graph.add_edge(0, 3)
graph.add_edge(1, 4)
graph.add_edge(3, 2)
graph.add_edge(2, 5)

### Test Case 1: Shortest Path

bfs_path, bfs_distance = graph.bfs_shortest_path(0, 5)
dfs_path, dfs_distance = graph.dfs_shortest_path(0, 5)
print(f"BFS Shortest Path from 0 to 3: {bfs_path}")
print(f"BFS Shortest distance from 0 to 3: {bfs_distance}")

print(f"DFS Shortest Path from 0 to 3: {dfs_path}")
print(f"DFS Shortest distance from 0 to 3: {dfs_distance}")

### Test Case 2: Number of Connected Components

num_components = graph.count_connected_components()
print(f"Number of connected components in the graph: {num_components}")

### Test Case 3: Bipartite Check

is_bipartite = graph.is_bipartite()
print(f"Is the large graph bipartite? {'Yes' if is_bipartite else 'No'}")

```

**Testing and Grading:** 

Please submit your lab work by pushing your code and results to a GitHub repository specifically created for the EECS 330 course. Follow the steps below to complete your submission:

1. **Create a Folder**: In your EECS 330 GitHub repository, create a new folder named `Lab-9`.
2. **Add Your Work**: Place all relevant `.py` and `.ipynb` files that contain your code and results into the `Lab-9` folder.
3. **Push to GitHub**: Ensure that you commit and push the `Lab-9` folder to your GitHub repository.

By following these steps, your lab work will be considered complete and submitted. Make sure all your code runs successfully, and the results are clearly documented in the notebooks.

**Submission and Deadline:** Please submit your work through GitHub by the specified deadline. Your grade will be based on the completeness and accuracy of the work submitted. Ensure that all code is functional and results are clearly presented. Grades will reflect the work as it appears in your repository.