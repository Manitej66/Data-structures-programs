# Stack

A stack is a useful data structure in programming. It is just like a pile of plates kept on top of each other.

Think about the things you can do with such a pile of plates

- Put a new plate on top
- Remove the top plate

## LIFO Principle of Stack

In programming terms, putting an item on top of the stack is called **"push"** and removing an item is called **"pop"**.

![represent the lifo principle by using push and pop operation](https://cdn.programiz.com/sites/tutorial2program/files/stack.png)

​																			**Stack Push and Pop Operations**

In the above image, although item 2 was kept last, it was removed first - so it follows **the Last In First Out(LIFO)** principle.





## Basic Operations of Stack



A stack is an object or more specifically an abstract data structure(ADT) that allows the following operations:

- `Push`: Add an element to the top of a stack
- `Pop`: Remove an element from the top of a stack
- `IsEmpty`: Check if the stack is empty
- `IsFull`: Check if the stack is full
- `Peek`: Get the value of the top element without removing it



## Working of Stack Data Structure

The operations work as follows:

1. A pointer called TOP is used to keep track of the top element in the stack.
2. When initializing the stack, we set its value to -1 so that we can check if the stack is empty by comparing `TOP == -1`.
3. On pushing an element, we increase the value of TOP and place the new element in the position pointed to by TOP.
4. On popping an element, we return the element pointed to by TOP and reduce its value.
5. Before pushing, we check if the stack is already full
6. Before popping, we check if the stack is already empty

![adding elements to the top of stack and removing elements from the top of stack](https://cdn.programiz.com/sites/tutorial2program/files/stack-operations.png)                                                                                    

​																			**Working of Stack Data Structure**

The operations work as follows:

1. A pointer called TOP is used to keep track of the top element in the stack.

2. When initializing the stack, we set its value to -1 so that we can check if the stack is empty by comparing `TOP == -1`.

3. On pushing an element, we increase the value of TOP and place the new element in the position pointed to by TOP.

4. On popping an element, we return the element pointed to by TOP and reduce its value.

5. Before pushing, we check if the stack is already full

6. Before popping, we check if the stack is already empty

   ![adding elements to the top of stack and removing elements from the top of stack](https://cdn.programiz.com/sites/tutorial2program/files/stack-operations.png)																	          **Working of Stack Data Structure**



## Stack Time Complexity

For the array-based implementation of a stack, the push and pop operations take constant time i.e. `O(1)` because there is only a movement of the pointer in both the cases.

------

## Applications of Stack Data Structure

Although stack is a simple data structure to implement, it is very powerful. The most common uses of a stack are:

- **To reverse a word** - Put all the letters in a stack and pop them out. Because of the LIFO order of stack, you will get the letters in reverse order.
- **In compilers** - Compilers use the stack to calculate the value of expressions like `2 + 4 / 5 * (7 - 9)` by converting the expression to prefix or postfix form.
- **In browsers** - The back button in a browser saves all the URLs you have visited previously in a stack. Each time you visit a new page, it is added on top of the stack. When you press the back button, the current URL is removed from the stack and the previous URL is accessed.



