
# EECS 330 Lab-4 (Part B)/Project-1 

#### This is a 2-week lab including part A and part B.

## Goal: _Applying and Testing Data Structures Deque_

### Due date (based on your lab time):
- Monday 09/16/2024
  - Due on Friday 09/27/2024 11:59 pm
- Tuesday 09/17/2024
  - Due on Saturday 09/28/2024 11:59 pm
- Wednesday 09/18/2024
  - Due on Sunday 29/23/2023 11:59 pm
- Friday 09/20/2023
  - Due on Tuesday 10/1/2024 11:59 pm

##### NOTE: Import the Deque class from the previous Lab 4. (import Deque from Lab4)


### A. WordToDeque

Create a function named `wordToDeque()` that takes a single input parameter, which is a string. This function is responsible for sequentially adding each character of the input string to a deque. For instance, if the input string is 'hello', the method should add the characters to the deque in the order 'h - e - l - l - o.' Subsequently, perform a test on the `wordToDeque()` function to confirm that the deque matches the original string, with the front pointer positioned at 'h' and the back pointer at 'o'.

```Python
def wordToDeque(input):
    deque = Deque()
    # Write your code here and return the Deque() object
    pass
```

Testing logic:

```Python
def testWordToDeque(test_string, test_deque):
    temp = test_deque
    for i in range(len(test_string)):
        if temp.front == None or test_string[i] != temp.front.item:
            return False
        else:
            temp.front = temp.front.next
    if temp.front != None:
        return False
    return True
test1_string = "hello"
test1_deque = wordToDeque(test1_string)
print(testWordToDeque(test1_string, test1_deque)) # Should return True
```

<!---
**Task2: CharacterComparator**

Create a method called equalChars() inside CharacterComparator which compares two characters and returns True or False.

For e.g.

```Python
equalChars(“a”, “a”) is True
equalChars(“b”, “c”) is False
```

Skeleton Code:

```Python
class CharacterComparator:
    def equalChars(self, x, y):
        return 
```
-->
<!---
**Task 2: isPalindrome using equalChars() from CharacterComparator**

Create a method isPalindrome() which takes input as string. Convert the input string to deque and check if a given string is a palindrome or not. 

```Python
def isPalindrome(input):
    cc = CharacterComparator()
    deque = wordToDeque(input)
    # Write your logic here
    return 
```

Testing Logic:

```Python
test_input = "racecar"
print(isPalindrome(test_input))  # prints True
test_input1 = "apurva"
print(isPalindrome(test_input1)) # prints False
```
-->

### B. OffByOne

Create a function OffByOne() which accepts two parameters and check whether those two characters differ by one or not. Attention: you need to use the deque to implement this function. 

For e.g.

```Python
OffByOne(“a” , “b”) is True
OffByOne(“g” , “f”) is True
OffByOne(“a” , “h”) is False
OffByOne(“z” , “a”) is False
```

Skeleton Code:

```Python
def OffByOne(char1, char2):
    # Write your logic here 
    pass 
```

Testing Logic:

```Python
char1 = 'b'
char2 = 'a'
print(OffByOne(char1, char2)) #print True
```

### C. OffByN

Create a function OffByN() which accepts three parameters and check those two characters differ by N. Attention: you need to use the deque to implement this function. 

For example:

```Python
N = 3 # set offset of N
OffByN(“a” , “d”) is True
OffByN(“h” , “e”) is True
OffByN(“a” , “a”) is False
OffByN(“y” , “z”) is False

```

Skeleton Code:

```Python
def OffByN(char1, char2, N):
    # Write your code here and return either True or False
    pass
```

Testing logic:

```Python
char1 = 'b'
char2 = 'e'
N = 3
print(OffByN(char1, char2, N)) #Prints True
```

**Testing and Grading:** 

Please submit your lab work by pushing your code and results to a GitHub repository specifically created for the EECS 330 course. Follow the steps below to complete your submission:

1. **Create a Folder**: In your EECS 330 GitHub repository, create a new folder named `Lab-4`.
2. **Add Your Work**: Place all relevant `.ipynb` notebook files that contain your code and results into the `Lab-4` folder.
3. **Push to GitHub**: Ensure that you commit and push the `Lab-4` folder to your GitHub repository.

By following these steps, your lab work will be considered complete and submitted. Make sure all your code runs successfully, and the results are clearly documented in the notebooks.

**Submission and Deadline:** Please submit your work through GitHub by the specified deadline. Your grade will be based on the completeness and accuracy of the work submitted. Ensure that all code is functional and results are clearly presented. Grades will reflect the work as it appears in your repository.