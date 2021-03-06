# Array
An array is simply a number of memory locations, each of which can store an item of data of the same data type and which are all referenced through the same variable name.

Following are the important terms to understand the concept of Array.
* **Element** − Each item stored in an array is called an element.
* **Index** − Each location of an element in an array has a numerical index, which is used to identify the element.

Array may be defined abstractly as finite order set of homogeneous elements. So we can say that there are finite numbers of elements in an array and all the elements are of same data type. Also array elements are ordered i.e. we can access a specific array element by an index.

## Content
* [Why do we need array?](#why-do-we-need-array)
* [Advantages of array](#advantages-of-array)
* [How to declare an array?](#how-to-declare-an-array)
* [How to initialize an array](#how-to-initialize-an-array)
* [Memory allocation of array](#memory-allocation-of-array)
* [Properties of array](#properties-of-array)
* [How to access elements of array](#how-to-access-elements-of-array)
* [Basic operations on array](#basic-operations-on-array)
  - [Traversing](#traversing)
  - [Insertion](#insertion)
  - [Deletion](#deletion)
  - [Searching](#searching)
  - [Update](#update)
* [Conclusion](#conclusion)

## Why do we need array?
In computer programming, the most of the cases requires to store the large number of data of similar type. To store such amount of data, we need to define a large number of variables. It would be very difficult to remember names of all the variables while writing the programs. Instead of naming all the variables with a different name, it is better to define an array and store all the elements into it.

## Advantages of array
* Array provides the single name for the group of variables of the same type therefore, it is easy to remember the name of all the elements of an array.
* Traversing an array is a very simple process, we just need to increment the base address of the array in order to visit each element one by one.
* Any element in the array can be directly accessed by using the index.

## How to declare an array??
```c
dataType arrayName[arraySize];
```
For example:
```c
int a[5];
```
Here, we declared an array, a, of integer type. And its size is 5. Meaning, it can hold 5 integer values.

It's important to note that the size and type of an array cannot be changed once it is declared.

## How to initialize an array?
It is possible to initialize an array during declaration. For example,
```c
int a[5] = { 23, 54, 67, 21, 88};
```

You can also initialize an array like this.

```c
int a[] = {12, 54, 67, 23, 32}
```
Here, I haven't specified the size. However, the compiler knows its size is 5 as we are initializing it with 5 elements.

## Memory allocation of Array
All the data elements of an array are stored at contiguous locations in the main memory. The name of the array represents the base address or the address of first element in the main memory. Each element of the array is represented by a proper indexing.

## Properties of array
* Each element is of same data type and carries a same size i.e. int = 4 bytes.
* Elements of the array are stored at contiguous memory locations where the first element is stored at the smallest memory location.
* Elements of the array can be randomly accessed since we can calculate the address of each element of the array with the given base address and the size of data element.

## How to access elements of array
You can access elements with the help of the index at which you stored them.

Suppose you declared an array a as above. The first element is a[0], the second element is a[1] and so on.

```c
printf(“%d\n”,a[0]);
```

## Basic operations on array
Following are the basic operations supported by an array.

### Traversing
This operation is to traverse through the elements of an array.

Following program traverses and prints the elements of an array:

```c
#include<stdio.h>

int main()
{
    int array[5] = {2, 6, 8, 3, 9};
    int i = 0;
    for (i >= 0; i < 5; i++){
        printf("array[%d] = %d \n", i, array[i]);
    }
}
```
### Insertion
Insert operation is to insert one or more data elements into an array. Based on the requirement, a new element can be added at the beginning, end, or any given index of array.

Here, we see a practical implementation of insertion operation, where we add data at the given position of the array −

Example

Following is the implementation of the above algorithm −

```c
#include<stdio.h>

int main()

{
    int array[5] = { 2, 6, 8, 3, 9};

    // initial size of array
    int n = 5;
    int i = 0;

    // element to be inserted
    int x = 4;

    // position at which the element has to be inserted
    int pos = 3;

    // increase the size by 1
    n++;

    // shift elements after the pos forward
    for (i = n - 1; i >= pos; i--)
        array[i] = array[i-1];

    // insert x at pos
    array[pos-1] = x;

    // print new array
    for (i = 0; i < n; i++)
        printf("%d ",array[i]);

}
```
### Deletion
Deletion refers to removing an existing element from the array and re-organizing all elements of an array.

Following is the implementation of the above algorithm −

```c
#include<stdio.h>
int main()

{
    int array[5] = { 2, 6, 8, 3, 9};

    // initial size of array
    int n = 5;
    int i = 0;

    // element to be deleted
    int x = 6;
    int index;

    // iterate the array elements using loop if any element matches the key, store the index

    for (i = 0; i < n-1; i++)
    {
        if (array[i] == x)
        {
            index = i;
            break;
         }
    }

    //shift all the element from index+1 by one position to the left
    for (i = index; i < n-1; i++)
        array[i] = array[i+1];

    // print new array
    for (i = 0; i < n-1; i++)
        printf("%d ",array[i]);
        
}
```

### Searching
You can perform a search for an array element based on its value or its index.

There are two searching techniques linear and binary. For simplicity, I am implementing linear search algorithm to search element in array.

```c
#include<stdio.h>
int main()
{
    int array[5] = { 2, 6, 8, 3, 9};

    // initial size of array
    int n = 5;
    int i = 0;

    // element to be searched
    int x = 6;
    int index;

    // iterate the array elements using loop if any element matches the key, store the index
    for (i = 0; i < n; i++)
    {
        if (array[i] == x)
        {
            index = i;
            break;
         }
    }

    // print the index of element
    printf("Element %d is found at %d",x,index + 1);

}
```

### Update
Update operation refers to updating an existing element from the array at a given index.

```c
#include<stdio.h>
int main()
{
    int array[5] = { 2, 6, 8, 3, 9};
    
    // initial size of array
    int n = 5;
    int i = 0;
    
    // element to be switched
    int x = 6;
    
    // element with which to be switched
    int y = 4;
    int index;
    
    // iterate the array elements using loop if any element matches the key, store the index
    for (i = 0; i < n-1; i++)
    {
        if (array[i] == x)
        {
            array[i] = y;
            break;
         }
    }
            
    // print the index of element
    for (i = 0; i < n; i++)
        printf("%d ",array[i]);
}
```

## Conclusion
Arrays store multiple elements of the same type with the same name.You can randomly access elements in the array using an index number.Array memory is predefined, so there is no extra memory loss.Arrays avoid memory overflow.2D arrays can efficiently represent the tabular data

The number of elements in an array should be predefinedAn array is static. It cannot alter its size after declaration.Insertion and deletion operation in an array is quite tricky as the array stores elements in continuous form.Allocating excess memory than required may lead to memory wastage.
