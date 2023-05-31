## Merge Sort

### Introduction:
Merge Sort is a popular sorting algorithm that follows the divide-and-conquer approach to sort an array of elements. It divides the array into smaller subarrays, sorts them recursively, and then merges the sorted subarrays to produce a final sorted result.

### Algorithm:
1. Divide the unsorted array into two halves by finding the middle index.
2. Recursively apply Merge Sort to sort the two halves independently.
3. Merge the sorted halves by comparing the elements and placing them in the correct order.
4. Continue merging until all the elements are properly sorted.

### Code Example (Python):
```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    
    return merge(left, right)

def merge(left, right):
    merged = []
    i = 0
    j = 0
    
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            merged.append(left[i])
            i += 1
        else:
            merged.append(right[j])
            j += 1

    while i < len(left):
        merged.append(left[i])
        i += 1

    while j < len(right):
        merged.append(right[j])
        j += 1

    return merged
```

### Example Usage:
```python
arr = [9, 5, 2, 7, 1, 8, 3, 6, 4]
sorted_arr = merge_sort(arr)
print("Sorted Array:", sorted_arr)
```

### Explanation:
The Merge Sort algorithm follows these steps:

- **Divide**: The unsorted array is divided into two halves by finding the middle index. This division process continues recursively until the subarrays contain only one element.

- **Conquer**: Recursively apply Merge Sort to sort the two halves independently. This step is performed until the base case of having subarrays with one element is reached.

- **Merge**: The sorted halves are merged by comparing the elements from both halves and placing them in the correct order. The merging process continues until all the elements from both halves are properly merged.

- **Termination**: The algorithm terminates when the merging process is completed, and the entire array is sorted.

The `merge_sort` function recursively divides the array into smaller subarrays and then calls the `merge` function to merge and sort the subarrays. The `merge` function takes two sorted subarrays (`left` and `right`) and merges them into a single sorted array.

### Time Complexity:
The time complexity of Merge Sort is O(n log n), where n is the number of elements in the array. The array is divided into halves in each recursion, and the merging process takes linear time.

### Space Complexity:
The space complexity of Merge Sort is O(n), where n is the number of elements in the array. The algorithm requires additional space to store the sorted subarrays during the merging process.

Merge Sort is a highly efficient sorting algorithm that guarantees a stable sort. It is widely used in various applications and serves as a foundation for more advanced sorting algorithms. Understanding its implementation and principles allows for effective sorting of large datasets and optimization of time complexity.