# Arrays

An array is collection of items stored at contiguous memory locations. The idea is to store multiple items of same type together. 

​																				(or)

 **array** is a data structure consisting of a collection of *elements* values or variable  identified by at least one *array index* or *key*



## C++ Array Declaration

```cpp
dataType arrayName[arraySize];
```

## Access Elements in C++ Array

In C++, each element in an array is associated with a number. The number is known as an array index. We can access elements of an array by using those indices.

```cpp
// syntax to access array elements
array[index];
```

![C++ Array Declaration](https://cdn.programiz.com/sites/tutorial2program/files/cpp-array-declaration.png)

## C++ Array Initialization

In C++, it's possible to initialize an array during declaration. For example,

```cpp
// declare and initialize and array
int x[6] = {19, 10, 8, 17, 9, 15};
```

![C++ Array Initialization](https://cdn.programiz.com/sites/tutorial2program/files/cpp-array-initialization.png)



## C++ Array Out of Bounds

If we declare an array of size 10, then the array will contain elements from index 0 to 9.

However, if we try to access the element at index 10 or more than 10, it will result in Undefined Behaviour.



## Example Program to Take Inputs from User and Store Them in an Array

```cpp
#include <iostream>
using namespace std;

int main() {
    int numbers[6];

    cout << "Enter 6 numbers: " << endl;

    //  store input from user to array
    for (int i = 0; i < 6; ++i) {
        cin >> numbers[i];
    }

    cout << "The numbers are: ";

    //  print array elements
    for (int n = 0; n < 6; ++n) {
        cout << numbers[n] << "  ";
    }

    return 0;
}
```

