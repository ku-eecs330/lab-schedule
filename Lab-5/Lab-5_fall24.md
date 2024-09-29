
# EECS 330 Lab-5/Disjoint Sets


## Goal: _Implementation and Testing of Disjoint Sets._

### Due date (based on your lab time):
- Monday 09/30/2024
  - Due on Friday 10/4/2024 11:59 pm
- Tuesday 10/1/2024
  - Due on Saturday 10/5/2024 11:59 pm
- Wednesday 10/2/2024
  - Due on Sunday 10/6/2024 11:59 pm
- Friday 10/4/2024
  - Due on Tuesday 10/8/2024 11:59 pm

### Disjoint sets.

In this lab, you’ll create `DisjointSet` class which will use “quick union” to solve the dynamic connectivity problem. Our implementation of the `DisjointSet` data structure will be the most advanced version from lecture, namely Weighted Quick Union.

### Union By Weight.
The “weight” refers to the size of set, that is number of elemnets in set. When union is applied on two nodes, the root node of the vertex with a larger size will be considred new root . Shorter tree will be merged under the taller tree and assign the root node of the taller tree as the root node for both vertices.

### Union By Rank.
The “rank” refers to the height of each vertex. When union is applied on two nodes, the root node of vertex (a.k.a. item) with a larger “rank” will be considred new root. Shorter tree will be merged under the taller tree. Root node of the taller tree will be assigned as the root node for both subtrees.

<!--- 
### Path Compression
After finding the root node, the parent node of all traversed elements updated to their root node. This optimizes search speed for the root node of the same element again, which only needs to traverse twice to find the root node of a vertex.
--->

### A. Implementation of Disjoint Set.
You have been given a skeleton of a Disjoint set. Following skeleton implements constructor for  "Disjoint Set".

Vertex array stores parent corresponing each vertex. Weight arrays is to store weight of each vertex.

<!--- 
Note: In disjoint sets 0-th index of array is ignored. vertex 1 corresponds 1st index of array/list. 
--->


```Python
class DisjointSet:
    def __init__(self, size):
        self.vertex = [i for i in range(size)]
        self.weight = [1] * size
```
**A.1 Implement Utility Methods**

* `def validate(v1)`: Check if `v1` is a valid index.
* `def size(v1)`: Return the size of the set `v1` belongs to.
* `def parent(v1)`: Return the parent of `v1`, if `v1` is  the root of a tree, return the negative size of the tree for which `v1` is the root.

**A.2 Implement isConnected**

Check if given 2 vertex are connected or not. Return True if connected, if not return False.
```Python
 def isConnected(self, v1, v2):
        #add code here
        pass
```

**A.3 Implement find**

 Returns the root of the set v1 belongs to.
```Python
    def find(self, v1):
        #add you code here
        pass
```

**A.4 Implement Union By Weight**

Connects two elements `v1` and `v2` together. `v1` and `v2` can be any valid elements, and a union-by-size heuristic is used. If the sizes of the sets are equal, tie break by connecting `v1`’s root to `v2`’s root. Unioning a vertex with itself or vertices that are already connected should not change the sets, but it may alter the internal structure of the data structure.


```Python
    def unionByWeight(self, v1, v2):
        #Add code here
        pass
```


**A.5 Implement Union By Rank**

Change `self.weight` to `self.rank` in `DisjointSet`. While applying union, set with higher rank will represent as root. Re-implement B.4 using rank mechanism.

```Python
    def unionByRank(self, v1, v2):
        #Add code here
        pass
```

### B. Find number of connected block sets in a given grid.

Given n blocks, some of them are connected, while some are not. If block 1 is connected directly with block 2, and block 2 is connected directly with block 3, then block 1 and 3 are connected.

You are given an `n x n` matrix `Connected` where `Connected[i][j] = 1` if the `i`-th block and the `j`-th block are directly connected, and `Connected[i][j] = 0` otherwise.

For example, shown by the below matrix. There are 4 blocks let say 0, 1, 2, 3. To check if block 0 is connected to block 1 consider index `i=0` and `j=1` and `Connected[0][1]=1` . Block 0 and 1 are connected. 

```
 [1,1,0,1]
 [1,1,0,0]
 [0,0,1,1]
 [1,0,1,1]
```

Here block 1 is connected to 2 and 4 :1--2--4 is a block set.

**B.1 Return a disjoint set using Conntected matrix as input**

Given the `DisjointSet` data structure you have, and `Connected` matrix showing the connectivity among blocks, write a method to construct a DisjointSet at one time.
```Python
def joinBlocks(self, Connected):
  pass
```

**B.2 Return the total number of block sets**

Return number of connected block sets avaialble in the grid.

```Python
def findBlockSets(self):
  pass
```
**B.3 Return number of blocks in a connected block set**

Return number of bolcks in block set where the inquiry blockid belongs to. if the blockid is not connected to any, then return 1.

```Python
def findBlockcount(self, blockid):
  pass

```

### C. Testing your code for disjoint sets
Below is the testing logic for your code
```Python
if __name__ == '__main__':
  # Tasks A
  uf = DisjointSet(10)
  # 0 1-2-5-6-7 3-8-9 4
  uf.unionbyrank(1, 2)
  uf.unionbyrank(2, 5)
  uf.unionbyrank(5, 6)
  uf.uunionbyweight(6, 7)
  uf.unionbyrank(3, 8)
  uf.unionbyweight(8, 9)
  print(uf.isConnected(1, 5))  # true
  print(uf.isConnected(5, 7))  # true
  print(uf.isConnected(4, 9))  # false
  # 0 1-2-5-6-7 3-8-9-4
  uf.unionByWeight(9, 4)
  print(uf.isConnected(4, 9))  # true

  # Tasks B
  Connected = [[1,1,0,1], [1,1,0,0], [0,0,1,1], [1,0,1,1]]
  uf = DisjointSet(4)
  uf.joinBlocks(Connected)
  uf.findBlockCount(1)
```
**Testing and Grading:** 

Please submit your lab work by pushing your code and results to a GitHub repository specifically created for the EECS 330 course. Follow the steps below to complete your submission:

1. **Create a Folder**: In your EECS 330 GitHub repository, create a new folder named `Lab-5`.
2. **Add Your Work**: Place all relevant `.py` and `.ipynb` files that contain your code and results into the `Lab-5` folder.
3. **Push to GitHub**: Ensure that you commit and push the `Lab-5` folder to your GitHub repository.

By following these steps, your lab work will be considered complete and submitted. Make sure all your code runs successfully, and the results are clearly documented in the notebooks.

**Submission and Deadline:** Please submit your work through GitHub by the specified deadline. Your grade will be based on the completeness and accuracy of the work submitted. Ensure that all code is functional and results are clearly presented. Grades will reflect the work as it appears in your repository.