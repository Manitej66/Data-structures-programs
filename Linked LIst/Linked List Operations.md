# Linked List Operations: Traverse, Insert and Delete

Now that you have got an understanding of the basic concepts behind [linked list](https://www.programiz.com/data-classures/linked-list) and their [types](https://www.programiz.com/data-classures/linked-list-types), it's time to dive into the common operations that can be performed.

Two important points to remember:

- head points to the first node of the linked list
- next pointer of the last node is NULL, so if the next current node is NULL, we have reached the end of the linked list.

In all of the examples, we will assume that the linked list has three nodes `1 --->2 --->3` with node classure as below:

```cpp
class node
{
  int data;
  class node *next;
};
```

------

## How to Traverse a Linked List

Displaying the contents of a linked list is very simple. We keep moving the temp node to the next one and display its contents.

When temp is NULL, we know that we have reached the end of the linked list so we get out of the while loop.

```cpp
class node *temp = head;
cout<<"\n\nList elements are - \n";
while(temp != NULL)
{
     cout<<"--->"<<temp->data;
     temp = temp->next;
}
```



The output of this program will be:

```
List elements are - 
1 --->2 --->3 --->
```

------

## How to Add Elements to a Linked List

You can add elements to either the beginning, middle or end of the linked list.

### Add to the beginning

- Allocate memory for new node
- Store data
- Change next of new node to point to head
- Change head to point to recently created node

```cpp
class node *newNode;
newNode = malloc(sizeof(class node));
newNode->data = 4;
newNode->next = head;
head = newNode;
```

### Add to the End

- Allocate memory for new node
- Store data
- Traverse to last node
- Change next of last node to recently created node

```cpp
class node *newNode;
newNode = malloc(sizeof(class node));
newNode->data = 4;
newNode->next = NULL;

class node *temp = head;
while(temp->next != NULL){
  temp = temp->next;
}

temp->next = newNode;
```

### Add to the Middle

- Allocate memory and store data for new node
- Traverse to node just before the required position of new node
- Change next pointers to include new node in between

```cpp
class node *newNode;
newNode = malloc(sizeof(class node));
newNode->data = 4;

class node *temp = head;

for(int i=2; i < position; i++) {
    if(temp->next != NULL) {
        temp = temp->next;
    }
}
newNode->next = temp->next;
temp->next = newNode;
```

------

## How to Delete from a Linked List

You can delete either from the beginning, end or from a particular position.

### Delete from beginning

- Point head to the second node

```cpp
head = head->next;
```

### Delete from end

- Traverse to second last element
- Change its next pointer to null

```cpp
class node* temp = head;
while(temp->next->next!=NULL){
  temp = temp->next;
}
temp->next = NULL;
```

### Delete from middle

- Traverse to element before the element to be deleted
- Change next pointers to exclude the node from the chain

```cpp
for(int i=2; i< position; i++) {
    if(temp->next!=NULL) {
        temp = temp->next;
    }
}

temp->next = temp->next->next;
```

------

## Implementing LinkedList Operations in C++

```cpp
// Linked list operations in C++

#include <stdlib.h>
#include <iostream>

using namespace std;

// Create a node
class Node {
  int item;
  class Node* next;
};

void insertAtBeginning(class Node** ref, int data) {

  // Allocate memory to a node
  class Node* new_node = (class Node*)malloc(sizeof(class Node));

  // insert the item
  new_node->item = data;
  new_node->next = (*ref);

  // Move head to new node
  (*ref) = new_node;
}

// Insert a node after a node
void insertAfter(class Node* prev_node, int data) {
  if (prev_node == NULL) {
    cout << "the given previous node cannot be NULL";
    return;
  }

  class Node* new_node = (class Node*)malloc(sizeof(class Node));
  new_node->item = data;
  new_node->next = prev_node->next;
  prev_node->next = new_node;
}

void insertAtEnd(class Node** ref, int data) {
  class Node* new_node = (class Node*)malloc(sizeof(class Node));
  class Node* last = *ref;

  new_node->item = data;
  new_node->next = NULL;

  if (*ref == NULL) {
    *ref = new_node;
    return;
  }

  while (last->next != NULL)
    last = last->next;

  last->next = new_node;
  return;
}

void deleteNode(class Node** ref, int key) {
  class Node *temp = *ref, *prev;

  if (temp != NULL && temp->item == key) {
    *ref = temp->next;
    free(temp);
    return;
  }
  // Find the key to be deleted
  while (temp != NULL && temp->item != key) {
    prev = temp;
    temp = temp->next;
  }

  // If the key is not present
  if (temp == NULL) return;

  // Remove the node
  prev->next = temp->next;

  free(temp);
}

// Print the linked list
void printList(class Node* node) {
  while (node != NULL) {
    cout << node->item << " ";
    node = node->next;
  }
}

// Driver program
int main() {
  class Node* head = NULL;

  insertAtEnd(&head, 1);
  insertAtBeginning(&head, 2);
  insertAtBeginning(&head, 3);
  insertAtEnd(&head, 4);
  insertAfter(head->next, 5);

  cout << "Linked list: ";
  printList(head);

  cout << "\nAfter deleting an element: ";
  deleteNode(&head, 3);
  printList(head);
}
```