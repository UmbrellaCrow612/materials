## Quick Sort

### Introduction:
Quick Sort is a widely used sorting algorithm that follows the divide-and-conquer approach. It works by selecting a pivot element from the array and partitioning the other elements into two subarrays, according to whether they are less than or greater than the pivot. The subarrays are then sorted recursively.

### Algorithm:
1. Choose a pivot element from the array. This selection can be done in various ways, such as selecting the first, middle, or last element of the array.
2. Partition the array into two subarrays: one with elements less than the pivot and one with elements greater than the pivot.
3. Recursively apply Quick Sort to the two subarrays created in the previous step.
4. Combine the sorted subarrays and the pivot to obtain the final sorted array.

### Code Example (Python):
```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    
    pivot = arr[len(arr) // 2]
    smaller = [x for x in arr if x < pivot]
    equal = [x for x in arr if x == pivot]
    greater = [x for x in arr if x > pivot]
    
    return quick_sort(smaller) + equal + quick_sort(greater)
```

### Example Usage:
```python
arr = [9, 5, 2, 7, 1, 8, 3, 6, 4]
sorted_arr = quick_sort(arr)
print("Sorted Array:", sorted_arr)
```

### Explanation:
The Quick Sort algorithm follows these steps:

- **Pivot Selection**: Choose a pivot element from the array. The selection of the pivot can vary, but commonly it is selected as the middle element of the array.

- **Partitioning**: Partition the array into two subarrays: one with elements less than the pivot and one with elements greater than the pivot. This partitioning process places the pivot in its final sorted position.

- **Recursion**: Recursively apply Quick Sort to the two subarrays created in the previous step. The Quick Sort algorithm is applied to each subarray until the base case of subarrays with one or no elements is reached.

- **Combining**: Combine the sorted subarrays and the pivot to obtain the final sorted array. This step concatenates the sorted subarrays in the order of smaller elements, pivot, and greater elements.

The `quick_sort` function recursively applies Quick Sort to sort the array. It selects the pivot and partitions the array into three subarrays: smaller, equal, and greater. The function then recursively applies Quick Sort to the smaller and greater subarrays and combines them with the equal subarray and pivot to produce the sorted array.

### Time Complexity:
The average time complexity of Quick Sort is O(n log n), where n is the number of elements in the array. In the average case, the partitioning process splits the array into nearly equal-sized subarrays, leading to efficient sorting.

However, in the worst case (when the pivot is consistently the smallest or largest element), the time complexity becomes O(n^2). This can be mitigated by using randomized pivot selection or other techniques.

### Space Complexity:
The space complexity of Quick Sort is O(log n) on average, where n is the number of elements in the array. The recursive calls and partitioning process consume additional memory on the call stack.

Quick Sort is a widely used sorting algorithm due to its efficiency and ease of implementation. It performs well in practice and is often the preferred choice for sorting large datasets. Understanding its implementation and principles allows for efficient sorting and optimization of time complexity.