# Bubble Sort

Bubble Sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements,
and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted.

### Some basic info:-

The algorithm compares each pair of adjacent items in the list.  
Each pass through the entire list is called an PASS, and by the end of the first pass the largest element in
the array is in its correct postion.  
So by the end of each pass the algorith makes sure another element is in it's correct postion.

```c
int main() {
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr)/sizeof(arr[0]);

    printf("Original array: \n");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }

    printf("Sorted array: \n");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```

We use "n-1" iteration because in an array with "n" elements we can observe "n-1" comparisons.  
In the second for loop we observe that we use "n-1-i" because we know that by the end of a pass one element is in its respective postion in the array, so we donot need to compare the element again.
SO, we use "n-1-i".

# Insertion Sort.

Insertion sort is a simple sorting algorithm that builds the final sorted array one element at a time.

```c
#include <stdio.h>

void insertionSort(int arr[], int n) {
    int i, key, j;
    for (i = 1; i < n; i++) {
        key = arr[i];
        j = i - 1;
        // Loop to comapre the key element with the sorted array.
      while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}

void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++)
        printf("%d ", arr[i]);
    printf("\n");
}

int main() {
    int arr[] = {12, 11, 13, 5, 6};
    int n = sizeof(arr) / sizeof(arr[0]);
    printf("Original array: \n");
    printArray(arr, n);
    insertionSort(arr, n);
    printf("Sorted array: \n");
    printArray(arr, n);

    return 0;
}
```

The algorithm begins by assuming that the first element in the array is already sorted(i = 1 as shown above). It considers the next element in the array as the key.  
The key element is compared with the elements to its left in the already sorted part of the array.  
If the key is smaller than the compared element, the compared element is moved one position to the right.  
This process is repeated until an element smaller than or equal to the key is found or the beginning of the array is reached.  
Once an element smaller than or equal to the key is found (or the beginning of the array is reached), the key is inserted at the position after the last shifted element.

## Advantages and Disadvantages

### Advantages

**Simple Implementation:** Insertion sort is easy to implement and understand. It is a good choice for small datasets or when simplicity is more critical than the efficiency of the sorting algorithm.  
**Efficient for Small Datasets:** For small datasets or partially sorted datasets, insertion sort can be more efficient than other more complex algorithms such as quicksort or merge sort.  
**Adaptive:** It is adaptive, meaning that it performs well on datasets that are already partially sorted.
