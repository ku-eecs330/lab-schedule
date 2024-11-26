# EECS 330 Lab-12 (Advanced Sorting)


## Goal: Implementation of Advanced Sorting Algorithms

### Due date (based on your lab time):
- Monday 12/2/2024
  - Due on Friday 12/6/2024 11:59 pm
- Tuesday 12/3/2024
  - Due on Saturday 12/7/2024 11:59 pm
- Wednesday 12/4/2024
  - Due on Sunday 12/8/2024 11:59 pm
- Friday 12/6/2024
  - Due on Tuesday 12/10/2024 11:59 pm

### A. Quick Sort
Quicksort is an efficient divide-and-conquer sorting algorithm that selects a pivot element, partitions the array into sub-arrays of elements less than and greater than this pivot, and then recursively sorts these partitions. Its average-case time complexity is O(n log n), making it one of the fastest sorting algorithms for large datasets. However, its worst-case complexity can reach O(n^2), particularly with poorly chosen pivot elements.


### Implementation of Sorting Algorithm.

Following skeleton implements constructors for "HashMap". Note that each value is inserted as a set of (key, value) in the hash bucket calculated based on key.

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
**Implement Quick Sort**

Implement the Quicksort algorithm focusing on the in-place partitioning process(In-place partitioning means rearranging the elements within the array itself, without the need for additional memory space for another array structure).

```Python
def quicksort(self, low, high):
        if low < high:
            pi = self.partition(low, high)  # Partitioning index
            self.quicksort(low, pi-1)  # Recursively sort elements before partition
            self.quicksort(pi+1, high)  # Recursively sort elements after partition

def partition(self, low, high):
        """
        Implements in-place partitioning around a pivot.
        Elements less than the pivot are moved to its left, and greater to its right.
        The pivot is chosen using the median_of_three method.
        It is crucial to rearrange the elements within the array itself,
        avoiding the use of additional arrays or significant extra space.
        low : Starting index, high : Ending index
        Returns the partitioning index.
        """
        pass  

def median_of_three(self, low, high):
        """
        Selects the median of the first, middle, and last elements as the pivot.
        This method is used to improve performance by avoiding worst-case scenarios.
        low : Starting index, high : Ending index
        Returns the index of the median element.
        """
        pass  
```



### B. Radix Sort

Radix sort is a non-comparative sorting algorithm that works by distributing elements into buckets according to their individual digits or radix. It functions by sorting the input numbers per one digit at a time. Please consider following skeleton for implementation.

```Python
def counting_sort(arr, exp):

    # Count occurrences of each digit.
    
    # Update count to store the position of the next occurrence.
    
    # Build the output array.


def radix_sort(arr):
    # Return if array is empty.
      
    # Find the maximum number to know the number of digits.
    max_num = max(arr)

    # Do counting sort for every digit.
    exp = 1
    while max_num // exp > 0:
        counting_sort(arr, exp)
        exp *= 10
```

```Python
# Example usage
arr = [234, 34, 34, 2, 1, 0, 2, 3422]
radix_sort(arr)
print("Sorted array:", arr)
# Sorted array: [0, 1, 2, 2, 34, 34, 234, 3422]
```
### Testing logic.
You will be tested based on following test cases.

```Python
# Test quick sorting technique
def is_sorted(arr):
    if arr == sorted(arr):
        return "Passed!"
    else:
        return "Failed!"


def test_quicksort():
    """Test the Quicksort algorithm"""
    seed_num = 43   
    seed(seed_num)  # Set the seed for reproducibility
    sorting = Sorting(10)
    for _ in range(10):
        sorting.add(randint(1, 100))

    sorting.quicksort(0, len(sorting.arr) - 1)  # Apply the Quicksort algorithm
    print("Quick Sort:", is_sorted(sorting.arr))

# Test case execution
test_quicksort()
```


```Python
# Test radix sorting technique
def test_radix_sort():
    # Test case 1
    arr1 = [234, 34, 34, 2, 1, 0, 2, 3422]
    radix_sort(arr1)
    assert arr1 == [0, 1, 2, 2, 34, 34, 234, 3422], f"Test case 1 failed: {arr1}"

    # Test case 2
    arr2 = [329, 457, 657, 839, 436, 720, 355]
    radix_sort(arr2)
    assert arr2 == [329, 355, 436, 457, 657, 720, 839], f"Test case 2 failed: {arr2}"

    # Test case 3
    arr3 = [1, 200, 3, 400, 5]
    radix_sort(arr3)
    assert arr3 == [1, 3, 5, 200, 400], f"Test case 3 failed: {arr3}"

    # Test case 4 (empty array)
    arr4 = []
    radix_sort(arr4)
    assert arr4 == [], f"Test case 4 failed: {arr4}"

    # Test case 5 (array with one element)
    arr5 = [42]
    radix_sort(arr5)
    assert arr5 == [42], f"Test case 5 failed: {arr5}"

    print("All test cases passed!")

# Run the test cases
test_radix_sort()
```

**Testing and Grading:** 
Please submit your lab work by pushing your code and results to a GitHub repository specifically created for the EECS 330 course. Follow the steps below to complete your submission:

1. **Create a Folder**: In your EECS 330 GitHub repository, create a new folder named `Lab-12`.
2. **Add Your Work**: Place all relevant `.py` and `.ipynb` files that contain your code and results into the `Lab-12` folder.
3. **Push to GitHub**: Ensure that you commit and push the `Lab-12` folder to your GitHub repository.

By following these steps, your lab work will be considered complete and submitted. Make sure all your code runs successfully, and the results are clearly documented in the notebooks.

**Submission and Deadline:** Please submit your work through GitHub by the specified deadline. Your grade will be based on the completeness and accuracy of the work submitted. Ensure that all code is functional and results are clearly presented. Grades will reflect the work as it appears in your repository.
