# LinkedList

A linked list data structure includes a series of connected nodes. Here, each node store the data and the address of the next node. For example,

<img src="https://cdn.programiz.com/sites/tutorial2program/files/linked-list-concept.png" />

You have to start somewhere, so we give the address of the first node a special name called **HEAD**.

Also, the last node in the linked list can be identified because its next portion points to **NULL**.

## Representation of LinkedList

Let's see how each node of the LinkedList is represented. Each node consists:

- A data item
- An address of another node

We wrap both the data item and the next node reference in a struct as:

```cpp
class node
{
  int data;
  class node *next;
};
```



Each struct node has a data item and a pointer to another struct node. Let us create a simple Linked List with three items to understand how this works.

## Example of Creating Linked List with three nodes

```cpp
// Linked list implementation in C++

#include <bits/stdc++.h>
using namespace std;

// Creating a node
class Node {
   public:
  int value;
  Node* next;
};

int main() {
  Node* head;
  Node* one = NULL;
  Node* two = NULL;
  Node* three = NULL;

  // allocate 3 nodes in the heap
  one = new Node();
  two = new Node();
  three = new Node();

  // Assign value values
  one->value = 1;
  two->value = 2;
  three->value = 3;

  // Connect nodes
  one->next = two;
  two->next = three;
  three->next = NULL;

  // print the linked list value
  head = one;
  while (head != NULL) {
    printf("%d ", head->value);
    head = head->next;
  }
}
```



In just a few steps, we have created a simple linked list with three nodes.

<img src="https://cdn.programiz.com/sites/tutorial2program/files/linked-list-with-data.png" alt="representing linked list by connecting each node with next node using address of next node"  />

## Linked List Complexity

Time Complexity

|              | Worst case | Average Case |
| :----------- | :--------- | :----------- |
| **Search**   | O(n)       | O(n)         |
| **Insert**   | O(1)       | O(1)         |
| **Deletion** | O(1)       | O(1)         |

Space Complexity: O(n)

------

## Linked List Applications

- Dynamic memory allocation
- Implemented in stack and queue
- In **undo** functionality of softwares
- Hash tables, Graphs.
