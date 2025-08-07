# Heap Sort in Python 🐍⛏️

This repository contains a simple and clean implementation of the **Heap Sort** algorithm in Python.

## 🔍 What is Heap Sort?

**Heap Sort** is a comparison-based sorting technique based on a **Binary Heap** data structure. It is similar to selection sort where we first find the maximum element and place it at the end. We repeat the same process for the remaining elements.

* **Time Complexity:** O(n log n)
* **Space Complexity:** O(1) – in-place sorting
* **Stable:** ❌ No

## 🧠 How it works

1. Build a **max heap** from the input data.
2. Extract the largest element (root of the heap) and place it at the end of the array.
3. Reduce the heap size and heapify the root again.
4. Repeat the process until the heap is empty.

## 📦 Code Example

```python
def heapify(arr, N, i):
    largest = i 
    l = 2 * i + 1     
    r = 2 * i + 2    
    if l < N and arr[largest] < arr[l]:
        largest = l
    if r < N and arr[largest] < arr[r]:
        largest = r
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i] 
        heapify(arr, N, largest)

def heapSort(arr):
    N = len(arr)
    for i in range(N//2-1, -1, -1):
        heapify(arr, N, i)
    for i in range(N-1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i] 
        heapify(arr, i, 0)

arr = [2, 3, 0, 4, 9, 6]
heapSort(arr)
print("Sorted array is:", arr)
```

## 🚀 Output

```
Sorted array is: [0, 2, 3, 4, 6, 9]
```

## 📂 Use Case

Ideal for learning basic sorting algorithms, data structures (heap), and in coding interview preparations.


