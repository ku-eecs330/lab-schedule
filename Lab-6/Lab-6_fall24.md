# EECS 330 Lab-6 (BST)


## Goal: Implementation of Binary Search Tree (BST)

### Due date (based on your lab time):
- Monday 10/07/2024
  - Due on Friday 10/11/2024 11:59 pm
- Tuesday 10/08/2024
  - Due on Saturday 10/12/2024 11:59 pm
- Wednesday 10/09/2024
  - Due on Sunday 10/13/2024 11:59 pm
- Friday 10/11/2024
  - Due on Tuesday 10/15/2024 11:59 pm

### Binary Search Tree - BST

BST is a binary tree (each nodes have two children at the most) which follows an important property - given any node N1 in the tree, all nodes on the left of N1 must have values less than or equal to the node N1's value and all nodes on the right of N1 must have values greater than or equal to the node N1's value.

<!--
**Complexity Analsysis:**
1. Search. `O(N)`.
2. insertion. `O(N)`.
3. Deletion. `O(N)`
4. Space. `O(N)`
5. However, balanced BSTs show `O(logN)` complexity in terms of search, insertion and deletion, which is much preferable than the unbalanced tree.
-->

### A. Implementation of BST.

Following skeleton implements constructors for "TreeNode" and "BinarySearchTree".
Notice that we have left and right pointers signifying implementation of
binary tree.

```Python
class TreeNode:
  def __init__(self, value):
    self.value = value
    self.left = None
    self.right = None

class BinarySearchTree:
  def __init__(self):
    self.root = None
    ```Number of Nodes in the Tree```
    self.size = 0
```

**A.1 Insert a node with value in BST**

```Python
def insert(self, key)::
  """Implement your insertion algo."""
  pass
```
**Please pay attention:** this BST will allow duplicate values (otherwise you won't be able to handle the testing cases). When you reach the nodes having the same value as your insertion, make it to the right child.

**A.2 Search a value in BST and return TreeNode**

Note that you have to return the first node using preorder traversal if multiple values are present.

```Python
def search(self, key) -> TreeNode:
  """Return TreeNode Corresponding to the value."""
  pass
```

<!--
**A.3 Implement Preorder Traversal**

Start at the root node, first visit the current node, and then traverse its left and right subtrees.
The operations should be in the following order: `Current Root -> Left Subtree -> Right Subtree`.

```Python
def preorder_traversal(self) -> list:
  """Implement preorder traversal."""
  pass
```
**A.4 Implement Inorder Traversal**

Start at the root node (current), traverse its left subtree, visit the current node, and then traverse its right subtree.
The operations should be in the following order: `Left Subtree -> Current Root -> Right Subtree`.

```Python
def inorder_traversal(self) -> list:
  """Implement inorder traversal."""
  pass
```

**A.5 Implement Postorder Traversal**

Start at the root node (current node), first traverse its left subtree, and then traverse its right subtree, and finally visit the current node.
The operations should be in the following order: `Left Subtree -> Right Subtree -> Current Root`.

```Python
def postorder_traversal(self) -> list:
  """Implement postorder traversal."""
  pass
```
--->
### B. Implementation of level-order Traversal.

You can traverse the tree level by level in a bredth first search fashion. Start at the root node and visit nodes level by level, from left to right including all the nodes in that level.
The order of operations is: `Level1 -> Level2 -> Level3 -> ... -> LevelN`.

```Python
def level_order_traversal(self) -> list:
  pass
```

### C. Implement TreeMap (SortedMap) using BST.

A `TreeMap` (or a `SortedMap`) using `BST` is a common data structure that leverages Binary Search Trees (`BSTs`) to implement a map interface where the keys are sorted according to the `BST` implementation. `TreeMap` contains `key` and `value` as member variables and the Tree is organized according to the "`key`". Following is the skeleton.

```Python
class TreeNode:
  def __init__(self, key, value):
    self.key = key
    self.value = value
    self.left = None
    self.right = None

class TreeMap:
  def __init__(self):
    self.root = None
```

For the above example `TreeMap` you need to implement `put` and `get` methods to add and aquire the value of a key respectively.


### Testing logic.

```Python
# Initialize BST.
bst = BinarySearchTree()

# Test inserting nodes
bst.insert(5)
bst.insert(3)
bst.insert(8)
bst.insert(2)
bst.insert(4)
bst.insert(7)
bst.insert(9)

# Test size method.
assert bst.size() == 7
assert bst.search(1) == None

# Test inserting additional nodes.
bst.insert(1)
bst.insert(6)

assert bst.size() == 9
assert bst.search(1).key == 1

# Finally, also test by inserting duplicate values.

# Test level order traversal with duplicates.
bst = BinarySearchTree()
bst.insert(5)
bst.insert(3)
bst.insert(8)
bst.insert(2)
bst.insert(4)
bst.insert(7)
bst.insert(9)
bst.insert(5)
bst.insert(7)
bst.insert(1)
bst.insert(6)
bst.insert(1)
bst.insert(6)

# Test level order traversal.
assert bst.level_order_traversal() == [5, 3, 8, 2, 4, 7, 9, 1, 5, 7, 1, 6, 6]

# TreeMap.

# Create a TreeMap
tree_map = TreeMap()

# Test putting and getting key-value pairs.
tree_map.put(3, "A")
tree_map.put(1, "B")
tree_map.put(2, "C")
tree_map.put(4, "D")

assert tree_map.get(2) == "C"
assert tree_map.get(1) == "B"
assert tree_map.get(4) == "D"
# Non-existent key should return None.
assert tree_map.get(5) is None
```

<!-- additional testing code
# Test inorder traversal.
assert bst.inorder_traversal() == [2, 3, 4, 5, 7, 8, 9]

# Test preorder traversal.
assert bst.preorder_traversal() == [5, 3, 2, 4, 8, 7, 9]

# Test postorder traversal.
assert bst.postorder_traversal() == [2, 4, 3, 7, 9, 8, 5]

# Test traversals after inserting additional nodes.
assert bst.inorder_traversal() == [1, 2, 3, 4, 5, 6, 7, 8, 9]
assert bst.preorder_traversal() == [5, 3, 2, 1, 4, 8, 7, 6, 9]
assert bst.postorder_traversal() == [1, 2, 4, 3, 6, 7, 9, 8, 5]
--->

**Testing and Grading:** 

Please submit your lab work by pushing your code and results to a GitHub repository specifically created for the EECS 330 course. Follow the steps below to complete your submission:

1. **Create a Folder**: In your EECS 330 GitHub repository, create a new folder named `Lab-6`.
2. **Add Your Work**: Place all relevant `.py` and `.ipynb` files that contain your code and results into the `Lab-6` folder.
3. **Push to GitHub**: Ensure that you commit and push the `Lab-6` folder to your GitHub repository.

By following these steps, your lab work will be considered complete and submitted. Make sure all your code runs successfully, and the results are clearly documented in the notebooks.

**Submission and Deadline:** Please submit your work through GitHub by the specified deadline. Your grade will be based on the completeness and accuracy of the work submitted. Ensure that all code is functional and results are clearly presented. Grades will reflect the work as it appears in your repository.