# What is Bubble Sort?

Bubble sort is an algorithm that compares the adjacent elements and swaps their positions if they are not in the intended order. The order can be ascending or descending.

<img src="https://codingcompiler.com/wp-content/uploads/2017/10/bubble-sort-in-c.png">

## C++ Implementation of Bubble Sort

```cpp
#include <iostream>

using namespace std;

// Function for bubble sort
void Bubble_Sort(int array[], int size)
{
    int temp, flag;
    // flag keeps track if any swap happened or not, if swap not happened then array is sorted and it will break out of the loop
    // and will save time from running for loop unnecessarily
    for (int i = 0; i < size - 1; i++)
    {
        flag = 0;
        for (int j = 0; j < size - i - 1; j++)
        {
            // Do swapping
            if (array[j] > array[j + 1])
            {
                temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
                flag++;
            }
        }
        if (!flag)
            break;
    }

}

// Function to print elements of array
void Print_Array(int array[], int size)
{
    for (int i = 0; i < size; i++)
        cout<<array[i]<<" ";

    cout<<endl;
}

// Driver Function
int main()
{
    int num;
    cout<<"Enter number of elements in your array: ";
    cin>>num;
    int array[num];
    cout<<"Enter your array: ";
    for (int i = 0; i < num; i++)
    {
        cin>>array[i];
    }
    Bubble_Sort(array, num);
    Print_Array(array, num);
    return 0;
}

/*INPUT:
Enter number of elements in your array: 7
Enter your array: 8
4
7
2
9
2
4
Output:
2 2 4 4 7 8 9*/
```
