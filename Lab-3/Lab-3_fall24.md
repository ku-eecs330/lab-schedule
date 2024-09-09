
# EECS 330 Lab-3


## Goal: _Linked Lists_

### Due date (based on your lab time):
- Monday 09/09/2024
  - Due on Friday 09/13/2024 11:59 pm
- Tuesday 09/10/2024
  - Due on Saturday 09/14/2024 11:59 pm
- Wednesday 09/11/2024
  - Due on Sunday 09/15/2024 11:59 pm
- Friday 09/13/2024
  - Due on Tuesday 09/17/2024 11:59 pm

### Implementation of linked list methods

Given the following sample coes:
```python
class SLList:
    class IntNode:
        def __init__(self, item, next_node):
            self.item = item # int
            self.next = next_node # IntNode
            
    def __init__(self):
        self.first = None # initialize an empty list

    def addFirst(self, item):
        self.first = self.IntNode(item, self.first)
```



**1.1 Insert an Item (25 pts)**

Implement method `SLList.insert()` which takes in an integer `item` and an integer `position`. It inserts `item` at the given `position`. If `position` is after the end of the list, insert the new node at the end. For example, if the SLList is 5 → 6 → 2, insert (10, 1) results in 5 → 10 → 6 → 2, and if the SLList is 5 → 6 → 2, insert (10, 7) results in 5 → 6 → 2 → 10. Additionally, for this problem assume that position is a non-negative integer.

```python
def insert (self, item, position):
```


**1.2 Reverse the List (25 pts)**

Add another method to the class `SLList.reverse()` that reverses the elements. Do this using the existing `IntNode` objects (you should not use new).

```python
def reverse(self):
```

**1.3 Replicate the List (25 pts)**

Write a non-destructive method `SLList.replicate()` that replaces the `item` at `position` with `item` copies of itself. For example, replicate (3 → 2 → 1]) would return 3 → 3 → 3 → 2 → 2 → 1. For this question assume that all elements of the array are positive.  ("non-destructive" means that you will create a new linked list without changing the old one).

```python
def replicate(self):
```
**1.4 Write the Testing Case (25 pts)**

Create and run tests on your 1.1, 1.2, 1.3 to ensure its correctness. For example:
```python
if __name__ == '__main__':
  L = SLList()
  L.addFirst(15)
  L.addFirst(10)
  L.addFirst(5)
  L.reverse()

  L_expect = SLList()
  L_expect.addFirst(5)
  L_expect.addFirst(10)
  L_expect.addFirst(15)	

  if L.equals(L_expect):
    print("Two lists are equal, tests passed")
  else:
    print("Two lists are not equal, tests failed")
```

You can see that you will need an `SLList.equals` method to evaluate if two lists are the same. Please write the function to compare two `SLList` objects in terms of their values.
```python
def equals(self, anotherList):
```

**1.4 (Extra) Another Implementation (10 pts)** 

If you wrote reverse iteratively, write a second version that uses recursion (you may need a helper method). If you wrote it recursively, write it iteratively.


**Testing and Grading:** 

Please submit your lab work by pushing your code and results to a GitHub repository specifically created for the EECS 330 course. Follow the steps below to complete your submission:

1. **Create a Folder**: In your EECS 330 GitHub repository, create a new folder named `Lab-3`.
2. **Add Your Work**: Place all relevant `.ipynb` notebook files that contain your code and results into the `Lab-3` folder.
3. **Push to GitHub**: Ensure that you commit and push the `Lab-3` folder to your GitHub repository.

By following these steps, your lab work will be considered complete and submitted. Make sure all your code runs successfully, and the results are clearly documented in the notebooks.

**Submission and Deadline:** Please submit your work through GitHub by the specified deadline. Your grade will be based on the completeness and accuracy of the work submitted. Ensure that all code is functional and results are clearly presented. Grades will reflect the work as it appears in your repository.