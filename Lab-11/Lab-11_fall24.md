# EECS 330 Lab-10 (Sorting Algorithms)


## Goal: Implementation of Sorting Algorithms

### Due date (based on your lab time):
- Monday 11/18/2024
  - Due on Friday 11/22/2024 11:59 pm
- Tuesday 11/19/2024
  - Due on Saturday 11/23/2024 11:59 pm
- Wednesday 11/20/2024
  - Due on Sunday 11/24/2024 11:59 pm
- Friday 11/22/2024
  - Due on Tuesday 11/26/2024 11:59 pm

### Sorting 
A Sorting Algorithm is used to rearrange a given array or list of elements according to a comparison operator on the elements

### Selection Sort
Selection sort is a simple and efficient sorting algorithm that works by repeatedly selecting the smallest (or largest) element from the unsorted portion of the list and moving it to the sorted portion of the list. Time complexity of this sorting algortihm is O(n^2).

### Heap Sort
Heap Sort is a comparison-based sorting algorithm that uses a binary heap data structure to build a "max-heap" or "min-heap" and then sorts the array by repeatedly removing the largest (for max-heap) or smallest (for min-heap) element from the heap and placing it at the end of the array. The heap is updated after each removal to maintain the heap property. Time complexity of this sorting algortihm is  O(n log n).

### Merge Sort
Merge sort is defined as a sorting algorithm that works by dividing an array into smaller subarrays, sorting each subarray, and then merging the sorted subarrays back together to form the final sorted array. Time complexity of this sorting algortihm is  O(n log n).

### A. Implementation of Sorting Algorithms.

Following skeleton implements constructors for "HashMap". Note thhat each value is inserted as a set of (key, value) in the hash bucket calculated based on key.

```Python
from random import randint, seed
import time

class Sorting:
    def __init__(self, size):
        self.arr = []  # Initialize an empty list
        self.size = size

    def add(self, element):
        if len(self.arr) < self.size:
            self.arr.append(element)
        else:
            print("Array is already full, cannot add more elements.")
```
**A.1 Implement Selection Sort**

```Python
def selection_sort(self): :
  """Implements selection sort"""
  pass
```

**A.2 Implement Heap Sort**
```Python
def max_heapify(self, n, i):
  """Implements Heapify for array"""
  pass
```
```Python
def heap_sort(self):
  """Implements Heap sort"""
  pass
```
**A.3 Implement Merge Sort**

When dealing with an array of an odd number of elements in the merge sort algorithm, calculate the middle index by taking the floor of the array length divided by 2
```Python
def merge_sort(self):
   """Implements Merge sort"""
  pass
```

### B. Runtime Analysis of each sorting algorithms
**B.1 Record the time taken**

Record time taken for each sorting algortihhm implemented for array sizes `10000`, `20000`, `30000`, `40000`, `50000`. Input numbers will be genrated by random int library. Output will be printed from `run_time_tests()`.

Implement a function "test_sorting_time()" in the Sorting class to record the running time. Hint: find the interval between the start and the end of sorting excution.
```Python
def test_sorting_time(self, sorting_method):-> Time
  pass
```
**B.2 Runtime complexity of each sorting algorithms**

Explain the difference of time taken for each sorting algorithm based on their analytic time cmplexity. (You can add your answer as a comments in code at end or markdown in jupyter notebook)

### Testing logic.

```Python
#Test Sorted array
def is_sorted(arr):
  if arr == sorted(arr):
    print("Passed!")
  else:
    print("Failed!")

# Test each sirting technique
def test_sort_algorithms(sorting_method, set_seed=None):
  if seed != None:
    seed(set_seed)
  sorting = Sorting(10)
  # Add 10 random elements
  for _ in range(10):
    sorting.add(randint(1, 100))
  # Apply the sorting algorithm
  if sorting_method == 'selection':
    sorting.selection_sort()
    print("Selection Sort:", is_sorted(sorting.arr))
  elif sorting_method == 'heap':
    sorting.heap_sort()
    print("Heap Sort:", is_sorted(sorting.arr))
  elif sorting_method == 'merge':
    sorting.merge_sort()
    print("Merge Sort:", is_sorted(sorting.arr))
        
#Test run time
def run_time_tests():
  seeding = 45
  array_sizes = [10000,20000,30000,40000,50000]
  methods = ['selection', 'heap', 'merge']
  print("Array Size\t\tSelection Sort\t\tHeap Sort\t\tMerge Sort")
  for size in array_sizes: 
    times = []
    for m in methods:
      sorting = Sorting(size)
      seed(seeding)
      for _ in range(size):
        sorting.add(randint(1, 50000))
      interval = sorting.test_sorting_time(m)
      times.append(interval)
    print(f"{size}\t\t{times[0]:.6f}\t\t{times[1]:.6f}\t\t{times[2]:.6f}")
        
#test case execution
seed_num = 43   
test_sort_algorithms('selection', seed_num)
test_sort_algorithms('heap', seed_num)
test_sort_algorithms('merge', seed_num)
run_time_tests()
```

**Testing and Grading:** You should submit your code via a GitHub repository created for EECS 330.
For this lab, create a folder named "Lab-10" and push all your `.py` files into that folder on the GitHub repository to complete your lab work. 

**Submission and Deadline:** Please submit through GitHub and grades will be posted based on completed work without any issues.
