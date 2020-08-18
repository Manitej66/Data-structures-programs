# Types of Linked Lists

There are three common types of Linked List.

1. [Singly Linked List](https://www.programiz.com/dsa/linked-list-types#singly)
2. [Doubly Linked List](https://www.programiz.com/dsa/linked-list-types#doubly)
3. [Circular Linked List](https://www.programiz.com/dsa/linked-list-types#circular)

------

## Singly Linked List

It is the most common. Each node has data and a pointer to the next node.

![singly linked list](https://cdn.programiz.com/sites/tutorial2program/files/linked-list-concept_0.png)Singly linked list

Node is represented as:

```cpp
class node {
    int data;
    class node *next;
}
```

A three-member singly linked list can be created as:

```cpp
/* Initialize nodes */
class node *head;
class node *one = NULL;
class node *two = NULL;
class node *three = NULL;

/* Allocate memory */
one = malloc(sizeof(class node));
two = malloc(sizeof(class node));
three = malloc(sizeof(class node));

/* Assign data values */
one->data = 1;
two->data = 2;
three->data = 3;

/* Connect nodes */
one->next = two;
two->next = three;
three->next = NULL;

/* Save address of first node in head */
head = one;
```

------

## Doubly Linked List

We add a pointer to the previous node in a doubly-linked list. Thus, we can go in either direction: forward or backward.

![doubly linked list](https://cdn.programiz.com/sites/tutorial2program/files/doubly-linked-list-concept.png)Doubly linked list



A node is represented as

```cpp
class node {
    int data;
    class node *next;
    class node *prev;
}
```

A three-member doubly linked list can be created as

```cpp
/* Initialize nodes */
class node *head;
class node *one = NULL;
class node *two = NULL;
class node *three = NULL;

/* Allocate memory */
one = malloc(sizeof(class node));
two = malloc(sizeof(class node));
three = malloc(sizeof(class node));

/* Assign data values */
one->data = 1;
two->data = 2;
three->data = 3;

/* Connect nodes */
one->next = two;
one->prev = NULL;

two->next = three;
two->prev = one;

three->next = NULL;
three->prev = two;

/* Save address of first node in head */
head = one;
```

------

## Circular Linked List

A circular linked list is a variation of a linked list in which the last element is linked to the first element. This forms a circular loop.

![circular linked list](https://cdn.programiz.com/sites/tutorial2program/files/circular-linked-list.png)Circular linked list

A circular linked list can be either singly linked or doubly linked.

- for singly linked list, next pointer of last item points to the first item
- In the doubly linked list, prev pointer of the first item points to the last item as well.

A three-member circular singly linked list can be created as:

```cpp
/* Initialize nodes */
class node *head;
class node *one = NULL;
class node *two = NULL;
class node *three = NULL;

/* Allocate memory */
one = malloc(sizeof(class node));
two = malloc(sizeof(class node));
three = malloc(sizeof(class node));

/* Assign data values */
one->data = 1;
two->data = 2;
three->data = 3;

/* Connect nodes */
one->next = two;
two->next = three;
three->next = one;

/* Save address of first node in head */
head = one;
```

