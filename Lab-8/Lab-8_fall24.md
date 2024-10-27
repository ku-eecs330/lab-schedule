# EECS 330 Lab-8


## Goal: Implementation of Tree and Graph Traversals

### Due date (based on your lab time):
- Monday 10/28/2024
  - Due on Friday 11/1/2024 11:59 pm
- Tuesday 10/29/2024
  - Due on Saturday 11/2/2024 11:59 pm
- Wednesday 10/30/2024
  - Due on Sunday 11/3/2024 11:59 pm
- Friday 11/1/2024
  - Due on Tueday 11/5/2024 11:59 pm


### A. Implementation of Tree Traversal.

You are given a binary tree structure represented by the classes `TreeNode` and `BinaryTree`. Your task is to implement three different tree traversal algorithms: Preorder Traversal, Inorder Traversal, and Postorder Traversal. The `TreeNode` class defines the individual nodes with a value, a left child, and a right child, while the `BinaryTree` class manages the root node.

```Python
class TreeNode:
  def __init__(self, value):
    self.value = value
    self.left = None
    self.right = None

class BinaryTree:
    def __init__(self):
        self.root = None
```

**A.1 Implement Preorder Traversal**

 Implement the Preorder Traversal for the given binary tree. Preorder traversal involves visiting the current node first, then its left subtree, and finally its right subtree. The operations should be in the following order:  `Current Root -> Left Subtree -> Right Subtree`.

```Python
def preorder_traversal(self) -> list:
  """Implement preorder traversal."""
  pass
```
**A.2 Implement Inorder Traversal**

Implement the Inorder Traversal for the given binary tree. Inorder traversal involves visiting the left subtree first, then the current node, and finally the right subtree. The operations should be in the following order: `Left Subtree -> Current Root -> Right Subtree`.

```Python
def inorder_traversal(self) -> list:
  """Implement inorder traversal."""
  pass
```

**A.5 Implement Postorder Traversal**

Implement the Postorder Traversal algorithm for the given binary tree. Postorder traversal involves visiting the left subtree first, then the right subtree, and finally the current node. The operations should be in the following order: `Left Subtree -> Right Subtree -> Current Root`.

```Python
def postorder_traversal(self) -> list:
  """Implement postorder traversal."""
  pass
```

### Testing logic.

```Python

# Create a binary tree
bt = BinaryTree()
bt.root = TreeNode(1)
bt.root.left = TreeNode(2)
bt.root.right = TreeNode(3)
bt.root.left.left = TreeNode(4)
bt.root.left.right = TreeNode(5)
bt.root.right.left = TreeNode(6)
bt.root.right.right = TreeNode(7)
bt.root.left.left.left = TreeNode(8)
bt.root.left.left.right = TreeNode(9)
bt.root.right.right.right = TreeNode(10)

# Test the traversals
print("Preorder Traversal:", bt.preorder_traversal())
print("Inorder Traversal:", bt.inorder_traversal())    
print("Postorder Traversal:", bt.postorder_traversal())  


```

### B. Implementation of Graph Traversal.

You are provided with a graph represented as an adjacency list. The graph is defined using the Graph class with nodes and edges. Your task is to implement Depth-First Search (DFS) and Breadth-First Search (BFS) traversal algorithms for this graph.

```python
class Graph:
    def __init__(self, vertices):
        self.vertices = vertices
        self.adjacency_list = [[] for _ in range(vertices)]

    def add_edge(self, u, v):
        """Add an edge between vertices u and v."""
        pass
```

**B.1 Implement DFS**

Implement the Depth-First Search (DFS) traversal algorithm for the given graph. DFS explores as far as possible along each branch before backtracking.Your DFS implementation should start from a given source vertex and visit all reachable vertices.

```python
def dfs(self, source):
    """Implement Depth-First Search (DFS) starting from the source vertex."""
    pass

```
**B.2 Implement BFS**

 Implement the Breadth-First Search (BFS) traversal algorithm for the given graph. BFS explores all the vertices at the current level before moving to the next level.Your BFS implementation should start from a given source vertex and visit all reachable vertices.

```python
def bfs(self, source):
    """Implement Breadth-First Search (BFS) starting from the source vertex."""
    pass
```

### Testing logic.

```Python

# Create a graph with 20 vertices
graph = Graph(20)

# Add edges (change as needed)
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

# Test DFS and BFS from a source vertex
print("DFS from vertex 0:", graph.dfs(0))  
print("BFS from vertex 0:", graph.bfs(0))

# Create a graph with 4 vertices
graph = Graph(4)
graph.add_edge(0, 1)
graph.add_edge(0, 2)
graph.add_edge(1, 2)
graph.add_edge(2, 0)
graph.add_edge(2, 3)
graph.add_edge(3, 3)

# Test DFS and BFS from a source vertex
print("DFS from vertex 2:", graph.dfs(2))
print("BFS from vertex 2:", graph.bfs(2)) 
```

**Testing and Grading:** 

Please submit your lab work by pushing your code and results to a GitHub repository specifically created for the EECS 330 course. Follow the steps below to complete your submission:

1. **Create a Folder**: In your EECS 330 GitHub repository, create a new folder named `Lab-8`.
2. **Add Your Work**: Place all relevant `.py` and `.ipynb` files that contain your code and results into the `Lab-8` folder.
3. **Push to GitHub**: Ensure that you commit and push the `Lab-8` folder to your GitHub repository.

By following these steps, your lab work will be considered complete and submitted. Make sure all your code runs successfully, and the results are clearly documented in the notebooks.

**Submission and Deadline:** Please submit your work through GitHub by the specified deadline. Your grade will be based on the completeness and accuracy of the work submitted. Ensure that all code is functional and results are clearly presented. Grades will reflect the work as it appears in your repository.