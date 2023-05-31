# Comprehensive Guide to Stacks

## Introduction to Stack Data Structures

### Overview

A stack is a fundamental linear data structure that follows the Last-In-First-Out (LIFO) principle. It represents a collection of elements where the addition and removal of items occur only at one end, called the top of the stack. The last element added is the first one to be removed.

Stacks are incredibly versatile and find applications in various programming scenarios, including:

- Function call stack in programming languages.
- Undo/Redo operations in text editors or graphical interfaces.
- Evaluating arithmetic expressions.
- Backtracking algorithms and recursive function calls.
- Browser history navigation.

### Key Terminology

Before diving deeper into stacks, let's familiarize ourselves with some essential terminology:

- `Push:` Adding an element to the top of the stack.
- `Pop:` Removing the topmost element from the stack.
- `Top:` The reference to the top element in the stack.
- `Empty:` Indicates whether the stack is empty or contains elements.

## Implementing a Stack

### Stack Implementation

There are different ways to implement a stack, with the most common methods being using an array or a linked list.

**Array-based Implementation:**

- Declare an array of a fixed size or use dynamic resizing techniques.
- Keep track of the top index to efficiently perform push and pop operations.

**Linked List-based Implementation:**

- Create a node structure with a value and a reference to the next node.
- Maintain a reference to the top node to facilitate push and pop operations.

### Stack Operations and Complexity

Here are the key operations associated with stacks and their respective time complexities:

- `Push:` Adds an element to the top of the stack.

  - Array-based: O(1) time complexity on average (amortized) or O(n) in the worst-case scenario when resizing is required.
  - Linked List-based: O(1) time complexity.

- `Pop:` Removes the topmost element from the stack.

  - Array-based: O(1) time complexity.
  - Linked List-based: O(1) time complexity.

- `Top:` Retrieves the top element from the stack without removing it.

  - Array-based: O(1) time complexity.
  - Linked List-based: O(1) time complexity.

- `Empty:` Checks if the stack is empty.
  - Array-based: O(1) time complexity.
  - Linked List-based: O(1) time complexity.

## Stack Operations and Use Cases

### Example: Balancing Parentheses

Let's explore a practical example to demonstrate the use of stacks. We can employ a stack to check whether a string of parentheses is balanced or not. Here's how it works:

1. Iterate through the characters in the string.
2. If an opening parenthesis is encountered, push it onto the stack.
3. When a closing parenthesis is encountered, match it with the top of the stack.
4. If the parentheses are balanced, the stack will be empty at the end of the iteration.

### Example: Function Call Stack

The function call stack is a crucial aspect of program execution. It utilizes a stack to keep track of the program flow. Here's how it works:

1. When a function is called, its execution context is pushed onto the stack.
2. As each function completes, its context is popped from the stack, allowing the program to return to the previous function.

## Additional Stack Operations and Techniques

### Peek

The peek operation retrieves the top element from the stack without removing it. It can be useful when you need to examine the top element without modifying the stack.

### Stack Size

It's important to keep track of the size of the stack, especially in the array-based implementation, to

prevent stack overflow or underflow.

### Application: Infix to Postfix Conversion and Evaluation

Stacks can be employed to convert infix expressions (e.g., 3 + 4 _ 2) to postfix expressions (e.g., 3 4 2 _ +). Postfix expressions can then be evaluated using stacks to obtain the result.

## Stacks in Different Programming Languages

Stacks are widely used in various programming languages, albeit with some syntax and implementation differences. Let's explore stacks in a few popular programming languages:

### Stacks in Java

In Java, stacks can be implemented using the `java.util.Stack` class or the `java.util.Deque` interface, both of which provide stack functionality. Here's an example of creating and using a stack in Java:

```java
import java.util.Stack;

Stack<Integer> stack = new Stack<>();

stack.push(10); // Pushes an element onto the stack

stack.push(20);

stack.push(30);

int topElement = stack.peek(); // Retrieves the top element without removing it

int poppedElement = stack.pop(); // Removes and returns the top element

boolean isEmpty = stack.isEmpty(); // Checks if the stack is empty
```

### Stacks in Python

In Python, stacks can be implemented using built-in data structures like lists. Here's an example:

```python
stack = []

stack.append(10)  # Pushes an element onto the stack

stack.append(20)

stack.append(30)

topElement = stack[-1]  # Retrieves the top element without removing it

poppedElement = stack.pop()  # Removes and returns the top element

isEmpty = len(stack) == 0  # Checks if the stack is empty
```

### Stacks in C++

In C++, stacks can be implemented using the `std::stack` container adapter, part of the Standard Template Library (STL). Here's an example:

```c++
#include <stack>

std::stack<int> stack;

stack.push(10); // Pushes an element onto the stack

stack.push(20);

stack.push(30);

int topElement = stack.top(); // Retrieves the top element without removing it

stack.pop(); // Removes the top element

bool isEmpty = stack.empty(); // Checks if the stack is empty
```

### Stacks in JavaScript

In JavaScript, stacks can be implemented using arrays. Here's an example:

```javascript
let stack = [];

stack.push(10); // Pushes an element onto the stack

stack.push(20);

stack.push(30);

let topElement = stack[stack.length - 1]; // Retrieves the top element without removing it

let poppedElement = stack.pop(); // Removes and returns the top element

let isEmpty = stack.length === 0; // Checks if the stack is empty
```

These are just a few examples of how stacks can be implemented in different programming languages. For detailed information on stack usage and features in a particular programming language, it's essential to refer to language-specific documentation and resources.
