# EECS 330 Lab-7 (HashMAP)


## Goal: Implementation of Hashmap

### Due date (based on your lab time):
- Monday 10/21/2024
  - Due on Friday 10/25/2024 11:59 pm
- Tuesday 10/22/2024
  - Due on Saturday 10/26/2023 11:59 pm
- Wednesday 10/23/2024
  - Due on Sunday 10/27/2024 11:59 pm
- Friday 10/25/2024
  - Due on Tuesday 10/29/2024 11:59 pm

### HashMap 

A HashMap is a data structure that maps keys to their respective value pairs. It makes it easy to find values that are associated with their keys.

### Hashing with seperate chaining
Each location/bucket can be used to store multiple data objects organized using an auxiliary data structure. Each bucket in the hash table will then hold a pointer pointing to one of auxiliary data structures such as LinkedList, List, Array etc.

### A. Implementation of HashMap.

Following skeleton implements constructors for `HashMap`. Note that each value is inserted as a set of (key, value) in the hash bucket calculated based on key.

```Python
class HashMap:
    def __init__(self, size):
        self.size = size
        self.hash_table = [[] for _ in range(size)]

    def _hash_function(self, key):
        return hash(key) % self.size
```

**A.1 Insert a hash key,value in HashMap**

```Python
def put(self, key, value):
  """Implement your insertion algo."""
  pass
```

**A.2 Retrieve a value in HashMap**

```Python
def get(self, key) -> Int:
  """Return Corresponding value for Key"""
  pass
```
**A.3 Remove a value in HashMap**

```Python
def remove(self, key,value) :
  """Remove Corresponding value for Key"""
  pass
```
**A.4 Display List corresponding to a Key in HashMap**

```Python
def display(self) -> List[List]:
  """Display the updated hash map"""

```

### B. Trip with maximum number of passengers on flight

Imagine that we have a list of every commercial airline flight and its corresponsing set of trips, stored as a List. Each flight object stores a flight number, trip id, and a number of passengers on that trip. 

Flight number -> Int (Hash Key)
Trip id -> Alphha Numeric (Value1)
No.of Passenger ->Int (Value2)

```Python
class FlightNode:
    def __init__(self, flight_number, trip_id, passengers):
        self.flight_number = flight_number
        self.trip_id = trip_id
        self.passengers = passengers
```
Implement an algorithm using the HashMap implementation for finding the trip with largest number of passengers on the specified flight.

```Python
def max_passengers_in_flight(self, flight_number)-> (trip_id,passengers):
  pass
```

### Testing logic.

```Python
# Display the hash map
my_hash_map = HashMap(7)
0, 1, 4, 9, 16, 25, 36, 49, 64, 81
my_hash_map.put("aaa", 0)
my_hash_map.put("bbb", 1)
my_hash_map.put("ccc", 4)
my_hash_map.put("ddd", 9)
my_hash_map.put("eee", 16)
my_hash_map.put("fff", 25)
my_hash_map.put("ggg", 36)
my_hash_map.put("hhh", 49)
my_hash_map.put("ccc", 64)
my_hash_map.put("ccc", 81)
my_hash_map.display()  

# Retrieve values
print("Retrieve values:")
print("aaa:", my_hash_map.get("aaa"))  
print("bbb:", my_hash_map.get("bbb"))
print("ccc:", my_hash_map.get("ccc"))

# Remove a key-value pair
my_hash_map.remove("bbb", 1)  

# Display the updated hash map
my_hash_map.display() 

#Max Passengers on Trip
 my_map = HashMap(11)
# Add flight nodes (flight_number, trip_id, passengers)
my_map.put(16, FlightNode(16, "Trip 1", 300))
my_map.put(16, FlightNode(16, "Trip 2", 700))
my_map.put(29, FlightNode(29, "Trip 1", 800))
my_map.put(29, FlightNode(29, "Trip 2", 250))
my_map.put(36, FlightNode(29, "Trip 3", 500))
my_map.put(36, FlightNode(36, "Trip 1", 500))
my_map.put(36, FlightNode(36, "Trip 2", 340))
my_map.put(36, FlightNode(36, "Trip 3", 900))
my_map.put(36, FlightNode(36, "Trip 4", 400))
my_map.put(49, FlightNode(49, "Trip 1", 250))
my_map.put(49, FlightNode(49, "Trip 2", 550))

max_passengers = my_map.max_passengers_in_flight(49)
    if max_passengers is not None:
        print("Largest number of people in flight at once :", max_passengers)
    else:
        print("Flight not found in the map")

```

**Testing and Grading:** 

Please submit your lab work by pushing your code and results to a GitHub repository specifically created for the EECS 330 course. Follow the steps below to complete your submission:

1. **Create a Folder**: In your EECS 330 GitHub repository, create a new folder named `Lab-7`.
2. **Add Your Work**: Place all relevant `.py` and `.ipynb` files that contain your code and results into the `Lab-7` folder.
3. **Push to GitHub**: Ensure that you commit and push the `Lab-7` folder to your GitHub repository.

By following these steps, your lab work will be considered complete and submitted. Make sure all your code runs successfully, and the results are clearly documented in the notebooks.

**Submission and Deadline:** Please submit your work through GitHub by the specified deadline. Your grade will be based on the completeness and accuracy of the work submitted. Ensure that all code is functional and results are clearly presented. Grades will reflect the work as it appears in your repository.