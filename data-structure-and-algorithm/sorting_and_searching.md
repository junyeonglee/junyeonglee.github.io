# Sorting and Searching

## Merge Sort

```python
def sort(arr):
    helper = [None for _ in range(len(array))]
    mergesort(arr, helper, 0, len(arr) - 1)

def mergesort(arr, helper, low, high):
    if low < high:
        middle = int ((low + high) / 2)
        mergesort(arr, helper, low, middle)  # sort left half
        mergesort(arr, helper, middle + 1, high)  # sort right half
        merge(arr, helper, low, middle, high)  # merge them

def merge(arr, helper, low, middle, high):
    # copy both halves into a helper array
    for i in range(low, high + 1):
        helper[i] = arr[i]

    helper_left = low
    helper_right  = middle + 1
    current = low

    # iterate through helper array. Compare the left and right half, copying back
    # the smaller element from the two halves into the original array
    while helper_left <= middle and helper_right <= high:
        if helper[helper_left] <= helper[helper_right]:
            arr[current] = helper[helper_left]
            helper_left += 1
        else:  # if right element is smaller than left element
            arr[current] = helper[helper_right]
            helper_right += 1
        current += 1

    # copy the rest of the left side of the array into the target array
    remaining = middle - helper_left
    for i in range(remaining + 1):
        arr[current + i] = helper[helper_left + i]
```

## Quick Sort

```python
def quicksort(arr, left, right):
    index = partition(arr, left, right)
    if left < index - 1:  # Sort left half
        quicksort(arr, left, index - 1)
    if index < right:  # Sort right half
        quicksort(arr, index, right)

def partition(arr, left, right):
    pivot = int ((left + right) / 2)  # Pick pivot point

    while left <= right:
        while arr[left] < pivot:  # Find element on left that should be on right
            left = left + 1
        while arr[right] > pivot:  # Find element on right that should be on left
            right = right - 1

        if left <= right:
            swap(arr, left, right)  # Swap elements, and move left and right indices
            left = left + 1
            right = right - 1

    return left
```

## Searching Algorithms

```python
def binary_search(arr, x):
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2
        if x > arr[mid]:
            low = mid + 1
        elif x < arr[mid]:
            high = mid - 1
        else:
            return mid

    return -1  # Error

def binary_search_recursive(arr, x, low, high):
    if low > high:
        return -1  # Error
    
    mid = (low + high) // 2
    if x > a[mid]:
        return binary_search_recursive(arr, x, mid + 1, high)
    elif x < a[mid]:
        return binary_search_recursive(arr, x, low, mid - 1)
    else:
        return mid
```
