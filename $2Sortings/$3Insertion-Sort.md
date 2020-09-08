# Insertion Sort Algorithm

#### In this tutorial, you will learn how insertion sort works. Also, you will find working examples of insertion sort in C++.

Insertion sort works similarly as we sort cards in our hand in a card game.

We assume that the first card is already sorted then, we select an unsorted card. If the unsorted card is greater than the card in hand, it is placed on the right otherwise, to the left. In the same way, other unsorted cards are taken and put at their right place.

A similar approach is used by insertion sort.

Insertion sort is a sorting algorithm that places an unsorted element at its suitable place in each iteration.

------

## How Insertion Sort Works?

Suppose we need to sort the following array.

![Insertion Sort Steps](https://cdn.programiz.com/sites/tutorial2program/files/Frame%204_0.png)Initial array

1. The first element in the array is assumed to be sorted. Take the second element and store it separately in `key`.Compare `key`

    

   with the first element. If the first element is greater than  `key`   , then  `key`  is placed in front of the first element.

   ![Insertion Sort Steps](https://cdn.programiz.com/sites/tutorial2program/files/Insertion-sort-0_1.png)If the first element is greater than key, then key is placed in front of the first element.

2. Now, the first two elements are sorted.

   Take the third element and compare it with the elements on the left of it. Placed it just behind the element smaller than it. If there is no element smaller than it, then place it at the beginning of the array.

   ![Insertion Sort Steps](https://cdn.programiz.com/sites/tutorial2program/files/Insertion-sort-1_1.png)Place 1 at the beginning

3. Similarly, place every unsorted element at its correct position.

   ![Insertion Sort Steps](https://cdn.programiz.com/sites/tutorial2program/files/Insertion-sort-2_2.png)Place 4 behind 1

   ![Insertion Sort Steps](https://cdn.programiz.com/sites/tutorial2program/files/Insertion-sort-3_2.png)Place 3 behind 1 and the array is sorted

------

## Insertion Sort Algorithm

```
insertionSort(array)
  mark first element as sorted
  for each unsorted element X
    'extract' the element X
    for j <- lastSortedIndex down to 0
      if current element j > X
        move sorted element to the right by 1
    break loop and insert X here
end insertionSort
```

------

## Python, Java and C/C++ Examples

```c++
// Insertion sort in C++

#include <iostream>
using namespace std;

// Function to print an array
void printArray(int array[], int size) {
  for (int i = 0; i < size; i++) {
    cout << array[i] << " ";
  }
  cout << endl;
}

void insertionSort(int array[], int size) {
  for (int step = 1; step < size; step++) {
    int key = array[step];
    int j = step - 1;

    // Compare key with each element on the left of it until an element smaller than
    // it is found.
    // For descending order, change key<array[j] to key>array[j].
    while (key < array[j] && j >= 0) {
      array[j + 1] = array[j];
      --j;
    }
    array[j + 1] = key;
  }
}

// Driver code
int main() {
  int data[] = {9, 5, 1, 4, 3};
  int size = sizeof(data) / sizeof(data[0]);
  insertionSort(data, size);
  cout << "Sorted array in ascending order:\n";
  printArray(data, size);
}
```

------

## Complexity



**Time Complexities**

- **Worst Case Complexity:** `O(n2)`
  Suppose, an array is in ascending order, and you want to sort it in descending order. In this case, worst case complexity occurs.

  Each element has to be compared with each of the other elements so, for every nth element, `(n-1)` number of comparisons are made.

  Thus, the total number of comparisons = `n*(n-1) ~ n2`

- **Best Case Complexity:** `O(n)`
  When the array is already sorted, the outer loop runs for `n` number of times whereas the inner loop does not run at all. So, there are only `n` number of comparisons. Thus, complexity is linear.

- **Average Case Complexity:** `O(n2)`
  It occurs when the elements of an array are in jumbled order (neither ascending nor descending).

**Space Complexity**

Space complexity is `O(1)` because an extra variable `key` is used.

------

## Insertion Sort Applications

The insertion sort is used when:

- the array is has a small number of elements
- there are only a few elements left to be sorted