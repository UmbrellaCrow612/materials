## Stacks

A stack is a simple and commonly used data structure that follows the Last-In-First-Out (LIFO) principle. It represents a collection of elements where the last element added is the first one to be removed. Think of it as a stack of books, where the last book placed on top is the first one to be taken off.

### Structure and Operations

A stack can be visualized as a vertical structure with two primary operations:

- **Push**: Adding an element to the top of the stack.
- **Pop**: Removing the topmost element from the stack.

Additionally, there are other operations commonly associated with stacks:

- **Peek**: Inspecting the topmost element without removing it.
- **IsEmpty**: Checking if the stack is empty.
- **Size**: Determining the number of elements in the stack.

### Stack Implementation

There are several ways to implement a stack, but the most common approach is to use an array or a linked list.

#### Array-based Stack

In an array-based stack, you use a fixed-size array to store the elements. A variable, often called `top`, keeps track of the index of the topmost element in the stack.

- **Push**: To push an element onto the stack, you increment the `top` index, store the element in that position, and handle any overflow conditions if the stack exceeds its capacity.
- **Pop**: To pop an element, you retrieve the element at the `top` index, decrement `top`, and return the element. You may need to handle underflow conditions if the stack is empty.
- **Peek**: You return the element at the `top` index without modifying the stack.
- **IsEmpty**: You check if `top` is equal to -1, indicating an empty stack.
- **Size**: The size of the stack is the value of `top + 1`.

#### Linked List-based Stack

In a linked list-based stack, you use a linked list data structure where each node contains an element and a reference to the next node.

- **Push**: To push an element onto the stack, you create a new node, set its value to the element, make it the new head of the linked list, and adjust the references accordingly.
- **Pop**: To pop an element, you remove the head node, set the next node as the new head, and return the element of the removed node. You handle

underflow conditions if the stack is empty.

- **Peek**: You return the value of the head node without modifying the stack.
- **IsEmpty**: You check if the head node is null, indicating an empty stack.
- **Size**: You traverse the linked list, counting the number of nodes.

### Common Use Cases

Stacks are widely used in various algorithms and programming scenarios, including:

- **Function Call Stack**: Stacks play a vital role in managing function calls and their local variables. Each function call is pushed onto the stack, and when a function completes, it is popped off the stack, allowing for proper control flow.
- **Expression Evaluation**: Stacks can be used to evaluate expressions, especially infix, postfix, and prefix notations. Operators and operands are pushed onto the stack, and the appropriate order of operations is maintained.
- **Undo/Redo Operations**: Stacks enable the undo and redo functionality by storing the state of actions. Each action is pushed onto the stack, allowing for easy reversal and restoration of previous states.
- **Backtracking Algorithms**: Stacks are used in backtracking algorithms like depth-first search (DFS), where the stack keeps track of visited nodes and allows for efficient exploration of paths.

### Summary

Stacks are a fundamental data structure that follows the Last-In-First-Out (LIFO) principle. They are efficient for managing elements in a specific order and are commonly used in various algorithms and programming scenarios. By understanding stacks and their operations, you gain a versatile tool for organizing and manipulating data in a wide range of applications.
