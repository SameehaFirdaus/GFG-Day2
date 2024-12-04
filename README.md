# GFG-Day2
---
Difficulty: Easy
Source: 160 Days of Problem Solving
Tags:
  - Arrays
---

# 🚀 _Day 2. Move All Zeroes to End_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/move-all-zeroes-to-end-of-array0751)


## 💡 **Problem Description:**

Given an array `arr[]`, move all the zeros in the array to the end while maintaining the relative order of non-zero elements. The modification should be done **in-place**.

## 🔍 **Example Walkthrough:**

**Input:**
```
arr[] = [1, 2, 0, 4, 3, 0, 5, 0]
```

**Output:**  
```
[1, 2, 4, 3, 5, 0, 0, 0]
```

**Explanation:**  
The three zeros are moved to the end while the relative order of non-zero elements is maintained.

**Input:**
```
arr[] = [10, 20, 30]
```

**Output:**  
```
[10, 20, 30]
```

**Explanation:**  
No change in the array as there are no zeros.

**Input:**
```
arr[] = [0, 0]
```

**Output:**  
```
[0, 0]
```

**Explanation:**  
No change in the array as all elements are zeros.

## 🎯 **My Approach:**

1. **Two-Pointer Technique:**  
   - Use a pointer `nonZeroIndex` to track the position where the next non-zero element should be placed.
   - Traverse the array, and whenever a non-zero element is encountered, swap it with the element at the `nonZeroIndex` and increment the pointer.
   - This ensures all non-zero elements are shifted to the front, and zeros naturally move to the end.

2. **Edge Cases:**  
   - If the array contains no zeros, return the array as is.
   - If the array contains only zeros, no changes are needed.

## 🕒 **Time and Auxiliary Space Complexity**📝

- **Expected Time Complexity:** O(n), where `n` is the number of elements in the array. Each element is traversed once to determine its position.  
- **Expected Auxiliary Space Complexity:** O(1), as no additional space is used apart from a few variables.
  
## 📝 **Solution Code*
## Code (Python)

```python
class Solution:
    def pushZerosToEnd(self, arr):
        n = len(arr)
        nonZeroIndex = 0

        for i in range(n):
            if arr[i] != 0:
                arr[nonZeroIndex], arr[i] = arr[i], arr[nonZeroIndex]
                nonZeroIndex += 1
```
