
# EECS 330 Lab-4 (Part A)
#### This is a 2-week lab including part A and part B.

## Goal: _Implementation of deque using Doubly-Linked-List_

### Due date (based on your lab time):
- Monday 09/16/2024
  - Due on Friday 09/27/2024 11:59 pm
- Tuesday 09/17/2024
  - Due on Saturday 09/28/2024 11:59 pm
- Wednesday 09/18/2024
  - Due on Sunday 29/23/2023 11:59 pm
- Friday 09/20/2023
  - Due on Tuesday 10/1/2024 11:59 pm

### A. Design "Deque" using *Linked-List* data structure.

You have been given a skeleton of a Deque using 

*Doubly-Linked-List*. Deque (Double ended queue) is a 
"double-eneded" abstract datastructure that simulates "queue", allowing addition and deletion of
elements from front and from the back. Example: [[link](https://runestone.academy/ns/books/published/pythonds/BasicDS/WhatIsaDeque.html)]

<!---
**Complexity Analsysis:**
1. Addition and Removal from the beginning and from the end. `O(1)`.
2. Peek front and back. `O(1)`.
3. Check if empty and the size. `O(1)`
4. Random access (search). `O(N)`

Thus, linear double-ended queue is efficient for addition, removal, peek and to check size.
-->

### B. Implementation of Deque (using Doubly-Linked-List).

Following skeleton implements constructors for "Node" and "Deque".

Notice that we have `next`, and `previous` pointers signifying implementation of Doubly-Linked-List.

Attention: you can NOT use `list` and its methods. Assume you don't need to worry about `public` vs. `private` variables.

```Python
class Node:
  def __init__(self, data):
    self.item = data
    self.next = None
    self.prev = None

class Deque:
  def __init__(self):
    self.front = None
    self.back = None
    self.size = 0
```



**B.1 Check whether the deque is empty**

Return `True` if the container is empty, and `False` otherwise.

```Python
def empty(self):
  """Check whether the deque is empty."""
  pass
```

**B.2 Check the size**

Return the number of items in deque in `int` datatype.
```Python
def get_size(self) -> int:
  """Return total number of elements in deque."""
  pass
```

**B.3 Add element at front**

```Python
def push_front(self, data):
  """Push an element to the front of the deque."""
  pass
```
**B.4 Add element at the end**

```Python
def push(self, data):
  """Push an element at the back of the deque."""
  pass
```

**B.5 Remove element from the front**

Remove element from the front of the queue and return (`->int` signifies the return type
that can be changed according to the use case).

```Python
def pop_front(self) -> int:
  """Pop an element from the front of the deque."""
  pass
```

**B.6 Remove element from the end**

Remove element from the end of the queue and return (`->int` signifies the return type
that can be changed according to the use case).

```Python
def pop(self) -> int:
  """Pop an element from the back of the deque."""
  pass
```
**B.7 Access first element**

Access first element of the deque and return (`->int` signifies the return type
that can be changed according to the use case).

```Python
def front(self) -> int:
  """Access first element of deque."""
  pass
```

**B.8 Access last element**

Access first element of the deque and return (`->int` signifies the return type
that can be changed according to the use case).

```Python
def back(self) -> int:
  """Access last element of deque."""
  pass
```

### C. Implementation of deque (using `numpy.array`).

Following class constructor represents deque using `numpy.array`. Note that the array is
initialized with a fixed initial size (10 by default). The datatype of numpy array is `int`
(which can be changed according to your requirements).

```Python
class Deque:
  def __init__(self, capacity=10):
    self.capacity = capacity
    # Initialize front and rear pointers.
    self.front = -1
    self.back = -1
    # Initialize size of the deque.
    self.size = 0
    # Use a zero intialized NumPy array to store elements.
    self.array = np.zeros(self.capacity, dtype=object)
```

**C.1 Implement deque functions.**

Similar to the "deque using Doubly-Linked-Lists", you have to implement following functions
for "deque using `numpy.array`":

1. `empty(self)`
2. `get_size(self)`
3. `push_front(self, data)`
4. `push(self, data)`
5. `pop_fron(self)`
6. `pop(self)`

**C.2 Implement resize function.**

In addition to the above functions, you need to implement `resize` function for the deque.
As you are using fixed size numpy arrays, what if it exceeds the capacity? In that case, 
you should create a new numpy array (with double size), copy all elements from current numpy
array to the new one, and replace it with the current one.

```Python
def resize(self):
  ```Set the new capacity.```
  new_capacity = self.capacity * 2
  ```TODO: Create a new numpy array.```

  ```TODO: Copy elements from the old array to the new one.```
  
  ```TODO: Set memeber variables accordingly.```
  # self.front = xxx
  # self.back = xxx
  # self.capacity = xxx
  # self.array = xxx
```

### D. Implementation of `isPalindrome` using previously implemented deque.

Now, leverage the Deque datastrcture that you have created to implement `isPalindrome` function,
that checks whether given `string` is palindrome or not.

For e.g.

```Python
test1 = "racecar"
test2 = "hello"
print(is_palindrome(test1))  # True
print(is_palindrome(test2))  # False
```

Note that the input is case-sensitive. That is `Racecar` and `racecar` treated differently.

The function skeleton for your reference. Your code should leverage "your" deque class to implement
this function.

```Python
def isPalindrome(s: str) -> bool:
  
  # Initialize Deque using Deque class.
  deque = Deque()
  
  while not deque.empty():
    '''TODO: Implement your comparison logic.'''
  
  return True
  
```

### E. Implementation of Deque Reversal.

Deque Reversal reverses deque (using Doubly-Linked_List deque) and returns a "new" deque.

Skeleton Code:

```Python
def reverse_deque(deque):
    # Initialize an object for your new deque.
    reversed_deque = Deque()

    # TODO: Iterate through the deque and add items to reversed_deque.
    # The items should be added in the reverse order.
    # The new deque reversed_deque should contain elements in exact reverse
    # of your current deque.

    return reversed_deque
```

Testing logic:

```Python
deque = Deque()
deque.push(1)
deque.push(2)
deque.push(3)

reversed_deque = reverse_deque(deque)
while not reversed_deque.empty():
    print(reversed_deque.pop_front())  # Should output 3, 2, 1.
```
