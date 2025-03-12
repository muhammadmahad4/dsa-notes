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
