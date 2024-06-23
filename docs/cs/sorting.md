This page shows frequently used sorting algorithms, implemented in Python, with notes on time complexity.

## Bubble Sort
Time complexity: $O(N^2)$
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
```

## Insertion Sort
Time complexity: $O(N^2)$
```python
def insertion_sort(arr):
    n = len(arr)
    # start with second element (if exists)
    for i in range(1, n):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
```

## Selection Sort
Time complexity: $O(N^2)$
```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n - 1):
        min_idx = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]

```

## Quick Sort
- Average time complexity: $O(Nlog(N))$
- Worst case time comlexity: $O(N^2)$
- not stable

```python
def quick_sort(arr, low, high):
    if len(arr) == 1:
        return arr
    if low < high:
        pivot = partition(arr, low, high)
        quick_sort(arr, low, pivot - 1)
        quick_sort(arr, pivot + 1, high)

def partition(arr, low, high):
    pivot = arr[high]
    i = low - 1
    for j in range(low, high):
        if arr[j] <= pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    return i + 1

```

## Merge Sort
- Average time complexity: $O(Nlog(N))$
- stable

```python
def merge_sort(arr):
    n = len(arr)
    if n > 1:
        mid = n // 2
        left = arr[:mid]
        right = arr[mid:]

        merge_sort(left)
        merge_sort(right)

        i = j = k = 0
        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                arr[k] = left[i]
                i + 1
            else:
                arr[k] = right[j]
                j +=1
            k += 1
        while i < len(left):
            arr[k] = arr[i]
            i += 1
            k += 1
        while j < len(right):
            arr[k] = arr[j]
            j += 1
            k += 1

```

## Heap Sort
- Average time complexity: $O(Nlog(N))$

```python
def heap_sort(arr):
    n = len(arr)
    for i in range(n // 2 - 1, - 1, -1):
        heapify(arr, n, i)
    
    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]
        heapify(arr, i, 0)

def heapify(arr, n, i):
    # create a max heap
    largest = i
    left = 2 * i + 1
    right = 2 * i + 2

    if left < n and arr[largest] < arr[left]:
        largest = left
    if right < n and arr[largest] < arr[right]:
        largest = right
    
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)
```