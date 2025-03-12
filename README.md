Sure! Let’s dive into **vectors** in C++. Vectors are one of the most commonly used containers in the **Standard Template Library (STL)**. They are dynamic arrays that can resize themselves automatically when elements are added or removed.

---

## **1. What is a Vector?**
- A vector is a sequence container that encapsulates dynamic arrays.
- It provides **random access** to elements (like arrays) and supports dynamic resizing.
- Elements are stored contiguously in memory.

---

## **2. Including the Vector Library**
To use vectors, include the `<vector>` header:
```cpp
#include <vector>
```

---

## **3. Declaring a Vector**
- Syntax:
  ```cpp
  std::vector<data_type> vector_name;
  ```
- Example:
  ```cpp
  std::vector<int> numbers; // Declares an empty vector of integers
  ```

---

## **4. Common Vector Functions and Methods**

### **a. Initialization**
- **Empty Vector**:
  ```cpp
  std::vector<int> v1; // Empty vector
  ```
- **Vector with Size**:
  ```cpp
  std::vector<int> v2(5); // Vector of size 5 (all elements initialized to 0)
  ```
- **Vector with Size and Initial Value**:
  ```cpp
  std::vector<int> v3(5, 10); // Vector of size 5, all elements initialized to 10
  ```
- **Vector from Another Vector**:
  ```cpp
  std::vector<int> v4(v3); // Copy of v3
  ```
- **Vector from Initializer List**:
  ```cpp
  std::vector<int> v5 = {1, 2, 3, 4, 5}; // Vector initialized with values
  ```

---

### **b. Adding Elements**
- **`push_back()`**: Adds an element to the end of the vector.
  ```cpp
  v1.push_back(10); // Adds 10 to the end of v1
  ```
- **`emplace_back()`**: Similar to `push_back()`, but more efficient for objects.
  ```cpp
  v1.emplace_back(20); // Adds 20 to the end of v1
  ```
- **`insert()`**: Inserts an element at a specific position.
  ```cpp
  v1.insert(v1.begin() + 2, 30); // Inserts 30 at index 2
  ```

---

### **c. Accessing Elements**
- **`at()`**: Accesses an element at a specific index (with bounds checking).
  ```cpp
  int element = v1.at(2); // Accesses element at index 2
  ```
- **`operator[]`**: Accesses an element at a specific index (no bounds checking).
  ```cpp
  int element = v1[2]; // Accesses element at index 2
  ```
- **`front()`**: Accesses the first element.
  ```cpp
  int first = v1.front(); // Accesses the first element
  ```
- **`back()`**: Accesses the last element.
  ```cpp
  int last = v1.back(); // Accesses the last element
  ```

---

### **d. Removing Elements**
- **`pop_back()`**: Removes the last element.
  ```cpp
  v1.pop_back(); // Removes the last element
  ```
- **`erase()`**: Removes an element at a specific position or range.
  ```cpp
  v1.erase(v1.begin() + 2); // Removes element at index 2
  v1.erase(v1.begin(), v1.begin() + 3); // Removes first 3 elements
  ```
- **`clear()`**: Removes all elements.
  ```cpp
  v1.clear(); // Clears the vector
  ```

---

### **e. Size and Capacity**
- **`size()`**: Returns the number of elements in the vector.
  ```cpp
  int size = v1.size(); // Returns the size of the vector
  ```
- **`capacity()`**: Returns the current capacity of the vector (memory allocated).
  ```cpp
  int capacity = v1.capacity(); // Returns the capacity
  ```
- **`empty()`**: Checks if the vector is empty.
  ```cpp
  if (v1.empty()) {
      cout << "Vector is empty!" << endl;
  }
  ```
- **`resize()`**: Resizes the vector.
  ```cpp
  v1.resize(10); // Resizes the vector to 10 elements
  ```

---

### **f. Iterators**
- **`begin()`**: Returns an iterator to the first element.
  ```cpp
  auto it = v1.begin(); // Iterator to the first element
  ```
- **`end()`**: Returns an iterator to the end (one past the last element).
  ```cpp
  auto it = v1.end(); // Iterator to the end
  ```
- **`rbegin()`**: Returns a reverse iterator to the last element.
  ```cpp
  auto rit = v1.rbegin(); // Reverse iterator to the last element
  ```
- **`rend()`**: Returns a reverse iterator to the beginning (one before the first element).
  ```cpp
  auto rit = v1.rend(); // Reverse iterator to the beginning
  ```

---

### **g. Other Useful Functions**
- **`swap()`**: Swaps the contents of two vectors.
  ```cpp
  v1.swap(v2); // Swaps v1 and v2
  ```
- **`assign()`**: Assigns new values to the vector.
  ```cpp
  v1.assign(5, 100); // Assigns 5 elements with value 100
  ```

---

## **5. Example Code**
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    // Declare and initialize a vector
    vector<int> v = {1, 2, 3, 4, 5};

    // Add elements
    v.push_back(6);
    v.emplace_back(7);

    // Access elements
    cout << "Element at index 2: " << v.at(2) << endl;
    cout << "First element: " << v.front() << endl;
    cout << "Last element: " << v.back() << endl;

    // Remove elements
    v.pop_back(); // Removes the last element
    v.erase(v.begin() + 2); // Removes element at index 2

    // Print all elements
    cout << "Vector elements: ";
    for (int i : v) {
        cout << i << " ";
    }
    cout << endl;

    // Size and capacity
    cout << "Size: " << v.size() << endl;
    cout << "Capacity: " << v.capacity() << endl;

    return 0;
}
```

---

## **6. Key Points to Remember**
- Vectors are dynamic arrays that can resize automatically.
- Use `push_back()` or `emplace_back()` to add elements.
- Use `at()` or `operator[]` to access elements.
- Use `pop_back()` or `erase()` to remove elements.
- Use `size()` to get the number of elements and `capacity()` to get the allocated memory.

---

Let me know if you need further clarification or examples! 😊


Absolutely! Here’s a clean and organized format for your Word document notes on **Stacks in C++**. You can copy and paste this directly into your document.

---

# **Stacks in C++**

---

## **1. Introduction**
- A **stack** is a **Last-In-First-Out (LIFO)** data structure.
- Elements are added and removed from the **top** of the stack.
- C++ provides a built-in stack library in the **Standard Template Library (STL)**.

---

## **2. Including the Stack Library**
To use stacks in C++, include the `<stack>` header:
```cpp
#include <stack>
```

---

## **3. Declaring a Stack**
- Use the `std::stack` template class.
- Syntax:
```cpp
std::stack<data_type> stack_name;
```
- Example:
```cpp
std::stack<int> myStack; // Declares a stack of integers
```

---

## **4. Common Stack Operations**

### **a. Push (Insert Element)**
- Adds an element to the top of the stack.
- Syntax:
```cpp
stack_name.push(value);
```
- Example:
```cpp
myStack.push(10); // Adds 10 to the stack
myStack.push(20); // Adds 20 to the stack
```

---

### **b. Pop (Remove Top Element)**
- Removes the top element from the stack.
- Syntax:
```cpp
stack_name.pop();
```
- Example:
```cpp
myStack.pop(); // Removes the top element (20)
```

---

### **c. Top (Access Top Element)**
- Returns the top element of the stack.
- Syntax:
```cpp
stack_name.top();
```
- Example:
```cpp
int topElement = myStack.top(); // Returns 10
```

---

### **d. Check if Stack is Empty**
- Returns `true` if the stack is empty, otherwise `false`.
- Syntax:
```cpp
stack_name.empty();
```
- Example:
```cpp
if (myStack.empty()) {
    cout << "Stack is empty!" << endl;
}
```

---

### **e. Get Size of Stack**
- Returns the number of elements in the stack.
- Syntax:
```cpp
stack_name.size();
```
- Example:
```cpp
int size = myStack.size(); // Returns 1
```

---

## **5. Example Code**
```cpp
#include <iostream>
#include <stack>
using namespace std;

int main() {
    stack<int> myStack;

    // Push elements
    myStack.push(10);
    myStack.push(20);
    myStack.push(30);

    // Access top element
    cout << "Top element: " << myStack.top() << endl; // Output: 30

    // Pop element
    myStack.pop(); // Removes 30
    cout << "Top element after pop: " << myStack.top() << endl; // Output: 20

    // Check size
    cout << "Stack size: " << myStack.size() << endl; // Output: 2

    // Check if empty
    if (!myStack.empty()) {
        cout << "Stack is not empty!" << endl;
    }

    return 0;
}
```

---

## **6. Time Complexities**
| **Operation** | **Time Complexity** |
|---------------|---------------------|
| Push          | O(1)                |
| Pop           | O(1)                |
| Top           | O(1)                |
| Empty         | O(1)                |
| Size          | O(1)                |

---

## **7. Underlying Container**
- By default, `std::stack` uses `std::deque` as its underlying container.
- You can change it to other containers like `std::vector` or `std::list`:
```cpp
std::stack<int, std::vector<int>> myStack; // Uses vector as the underlying container
```

---

## **8. Applications of Stacks**
- Reversing a sequence.
- Implementing backtracking algorithms.
- Parsing expressions (e.g., infix to postfix conversion).
- Undo/Redo functionality in text editors.
- Function call stack in recursion.

---

## **9. Key Points to Remember**
- Stacks follow the **LIFO** principle.
- Use `push()` to add elements and `pop()` to remove elements.
- Always check if the stack is empty before calling `top()` or `pop()` to avoid runtime errors.
- `std::stack` is a **container adapter**, meaning it uses an underlying container (like `std::deque` or `std::vector`).

---

This format is clean, organized, and easy to read. You can customize it further if needed. Let me know if you’d like me to add more details or examples! 😊



Yes, C++ provides a **linked list** implementation in the **Standard Template Library (STL)** through the `std::list` class. It is a **doubly linked list**, meaning each element has pointers to both the previous and next elements.

---

## **1. Including the List Library**
To use linked lists, include the `<list>` header:
```cpp
#include <list>
```

---

## **2. Declaring a Linked List**
- Syntax:
  ```cpp
  std::list<data_type> list_name;
  ```
- Example:
  ```cpp
  std::list<int> myList; // Declares an empty linked list of integers
  ```

---

## **3. Common Linked List Functions and Methods**

### **a. Initialization**
- **Empty List**:
  ```cpp
  std::list<int> l1; // Empty list
  ```
- **List with Initializer List**:
  ```cpp
  std::list<int> l2 = {1, 2, 3, 4, 5}; // List initialized with values
  ```

---

### **b. Adding Elements**
- **`push_back()`**: Adds an element to the end of the list.
  ```cpp
  l1.push_back(10); // Adds 10 to the end of the list
  ```
- **`push_front()`**: Adds an element to the beginning of the list.
  ```cpp
  l1.push_front(5); // Adds 5 to the beginning of the list
  ```
- **`insert()`**: Inserts an element at a specific position.
  ```cpp
  auto it = l1.begin();
  advance(it, 2); // Move iterator to index 2
  l1.insert(it, 20); // Inserts 20 at index 2
  ```

---

### **c. Accessing Elements**
- **`front()`**: Accesses the first element.
  ```cpp
  int first = l1.front(); // Accesses the first element
  ```
- **`back()`**: Accesses the last element.
  ```cpp
  int last = l1.back(); // Accesses the last element
  ```

---

### **d. Removing Elements**
- **`pop_back()`**: Removes the last element.
  ```cpp
  l1.pop_back(); // Removes the last element
  ```
- **`pop_front()`**: Removes the first element.
  ```cpp
  l1.pop_front(); // Removes the first element
  ```
- **`erase()`**: Removes an element at a specific position or range.
  ```cpp
  auto it = l1.begin();
  advance(it, 2); // Move iterator to index 2
  l1.erase(it); // Removes element at index 2
  ```
- **`remove()`**: Removes all elements with a specific value.
  ```cpp
  l1.remove(10); // Removes all elements with value 10
  ```
- **`clear()`**: Removes all elements.
  ```cpp
  l1.clear(); // Clears the list
  ```

---

### **e. Size and Capacity**
- **`size()`**: Returns the number of elements in the list.
  ```cpp
  int size = l1.size(); // Returns the size of the list
  ```
- **`empty()`**: Checks if the list is empty.
  ```cpp
  if (l1.empty()) {
      cout << "List is empty!" << endl;
  }
  ```

---

### **f. Iterators**
- **`begin()`**: Returns an iterator to the first element.
  ```cpp
  auto it = l1.begin(); // Iterator to the first element
  ```
- **`end()`**: Returns an iterator to the end (one past the last element).
  ```cpp
  auto it = l1.end(); // Iterator to the end
  ```
- **`rbegin()`**: Returns a reverse iterator to the last element.
  ```cpp
  auto rit = l1.rbegin(); // Reverse iterator to the last element
  ```
- **`rend()`**: Returns a reverse iterator to the beginning (one before the first element).
  ```cpp
  auto rit = l1.rend(); // Reverse iterator to the beginning
  ```

---

### **g. Other Useful Functions**
- **`sort()`**: Sorts the list.
  ```cpp
  l1.sort(); // Sorts the list in ascending order
  ```
- **`reverse()`**: Reverses the list.
  ```cpp
  l1.reverse(); // Reverses the list
  ```
- **`merge()`**: Merges two sorted lists.
  ```cpp
  std::list<int> l2 = {6, 7, 8};
  l1.merge(l2); // Merges l2 into l1
  ```
- **`unique()`**: Removes duplicate consecutive elements.
  ```cpp
  l1.unique(); // Removes duplicates
  ```

---

## **4. Example Code**
```cpp
#include <iostream>
#include <list>
using namespace std;

int main() {
    // Declare and initialize a list
    list<int> l = {1, 2, 3, 4, 5};

    // Add elements
    l.push_back(6);
    l.push_front(0);

    // Access elements
    cout << "First element: " << l.front() << endl;
    cout << "Last element: " << l.back() << endl;

    // Remove elements
    l.pop_back(); // Removes the last element
    l.pop_front(); // Removes the first element

    // Insert element
    auto it = l.begin();
    advance(it, 2); // Move iterator to index 2
    l.insert(it, 20); // Inserts 20 at index 2

    // Print all elements
    cout << "List elements: ";
    for (int i : l) {
        cout << i << " ";
    }
    cout << endl;

    // Sort the list
    l.sort();
    cout << "Sorted list: ";
    for (int i : l) {
        cout << i << " ";
    }
    cout << endl;

    return 0;
}
```

---

## **5. Key Points to Remember**
- `std::list` is a **doubly linked list**.
- Use `push_back()` and `push_front()` to add elements.
- Use `pop_back()` and `pop_front()` to remove elements.
- Use iterators to traverse the list.
- Use `sort()` and `reverse()` for sorting and reversing the list.

---

Let me know if you need further clarification or examples! 😊


The **`std::map`** in C++ is a powerful container from the **Standard Template Library (STL)** that stores elements as **key-value pairs**. It is implemented as a **balanced binary search tree** (usually a Red-Black Tree), so elements are always sorted by their keys.

---

## **1. Including the Map Library**
To use `std::map`, include the `<map>` header:
```cpp
#include <map>
```

---

## **2. Declaring a Map**
- Syntax:
  ```cpp
  std::map<key_type, value_type> map_name;
  ```
- Example:
  ```cpp
  std::map<string, int> myMap; // Declares a map with string keys and integer values
  ```

---

## **3. Common Map Methods and Functions**

### **a. Inserting Elements**
- **`insert()`**: Inserts a key-value pair into the map.
  ```cpp
  myMap.insert({"apple", 10});
  myMap.insert(make_pair("banana", 20));
  ```
- **`operator[]`**: Inserts or updates a key-value pair.
  ```cpp
  myMap["cherry"] = 30; // Inserts or updates the value for key "cherry"
  ```

---

### **b. Accessing Elements**
- **`operator[]`**: Accesses the value associated with a key. If the key doesn't exist, it inserts the key with a default value.
  ```cpp
  int value = myMap["apple"]; // Accesses the value for key "apple"
  ```
- **`at()`**: Accesses the value associated with a key. Throws an exception if the key doesn't exist.
  ```cpp
  int value = myMap.at("banana"); // Accesses the value for key "banana"
  ```

---

### **c. Checking for Existence**
- **`find()`**: Returns an iterator to the key-value pair if the key exists, otherwise returns `end()`.
  ```cpp
  auto it = myMap.find("cherry");
  if (it != myMap.end()) {
      cout << "Key found! Value: " << it->second << endl;
  } else {
      cout << "Key not found!" << endl;
  }
  ```

---

### **d. Removing Elements**
- **`erase()`**: Removes a key-value pair by key or iterator.
  ```cpp
  myMap.erase("apple"); // Removes the key "apple"
  auto it = myMap.find("banana");
  if (it != myMap.end()) {
      myMap.erase(it); // Removes the key-value pair using an iterator
  }
  ```
- **`clear()`**: Removes all elements from the map.
  ```cpp
  myMap.clear(); // Clears the map
  ```

---

### **e. Size and Capacity**
- **`size()`**: Returns the number of key-value pairs in the map.
  ```cpp
  int size = myMap.size(); // Returns the size of the map
  ```
- **`empty()`**: Checks if the map is empty.
  ```cpp
  if (myMap.empty()) {
      cout << "Map is empty!" << endl;
  }
  ```

---

### **f. Iterating Over a Map**
- Use iterators to traverse the map.
  ```cpp
  for (auto it = myMap.begin(); it != myMap.end(); it++) {
      cout << it->first << ": " << it->second << endl;
  }
  ```
- Use range-based for loops (C++11 and later):
  ```cpp
  for (auto& pair : myMap) {
      cout << pair.first << ": " << pair.second << endl;
  }
  ```

---

### **g. Other Useful Functions**
- **`count()`**: Returns the number of elements with a specific key (0 or 1 for `std::map`).
  ```cpp
  if (myMap.count("cherry")) {
      cout << "Key exists!" << endl;
  }
  ```
- **`lower_bound()`**: Returns an iterator to the first element with a key **not less than** the given key.
  ```cpp
  auto it = myMap.lower_bound("banana");
  if (it != myMap.end()) {
      cout << "Lower bound: " << it->first << ": " << it->second << endl;
  }
  ```
- **`upper_bound()`**: Returns an iterator to the first element with a key **greater than** the given key.
  ```cpp
  auto it = myMap.upper_bound("banana");
  if (it != myMap.end()) {
      cout << "Upper bound: " << it->first << ": " << it->second << endl;
  }
  ```

---

## **4. Example Code**

```cpp
#include <iostream>
#include <map>
using namespace std;

int main() {
    // Declare a map
    map<string, int> myMap;

    // Insert elements
    myMap.insert({"apple", 10});
    myMap.insert(make_pair("banana", 20));
    myMap["cherry"] = 30;

    // Access elements
    cout << "Value of apple: " << myMap["apple"] << endl;
    cout << "Value of banana: " << myMap.at("banana") << endl;

    // Check if a key exists
    if (myMap.find("cherry") != myMap.end()) {
        cout << "Cherry found!" << endl;
    }

    // Iterate over the map
    cout << "Map contents:" << endl;
    for (auto& pair : myMap) {
        cout << pair.first << ": " << pair.second << endl;
    }

    // Remove an element
    myMap.erase("banana");

    // Check size
    cout << "Size of map: " << myMap.size() << endl;

    // Clear the map
    myMap.clear();
    cout << "Map is empty: " << (myMap.empty() ? "Yes" : "No") << endl;

    return 0;
}
```

---

## **5. Output**
For the example above, the output will be:
```
Value of apple: 10
Value of banana: 20
Cherry found!
Map contents:
apple: 10
banana: 20
cherry: 30
Size of map: 2
Map is empty: Yes
```

---

## **6. Key Points**
- `std::map` stores elements as **key-value pairs**.
- Keys are **unique** and sorted in ascending order by default.
- Use `insert()` or `operator[]` to add elements.
- Use `find()` to check if a key exists.
- Use iterators or range-based loops to traverse the map.

Let me know if you need further clarification or examples! 😊
