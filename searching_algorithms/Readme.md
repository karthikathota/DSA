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
