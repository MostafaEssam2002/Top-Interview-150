## Problem Description
You are given two integer arrays `nums1` and `nums2`, sorted in non-decreasing order, and two integers `m` and `n`, representing the number of elements in `nums1` and `nums2`, respectively.

The task is to merge `nums1` and `nums2` into a single array sorted in non-decreasing order. The result should be stored inside `nums1` in-place. `nums1` has a length of `m + n`, where the first `m` elements are the ones to be merged, and the last `n` elements are set to `0` and should be ignored. `nums2` has a length of `n`.

### Examples
**Example 1**  
Input:  
`nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3`  
Output:  
`[1,2,2,3,5,6]`  
Explanation: The arrays to merge are `[1,2,3]` and `[2,5,6]`.  

**Example 2**  
Input:  
`nums1 = [1], m = 1, nums2 = [], n = 0`  
Output:  
`[1]`  
Explanation: The arrays to merge are `[1]` and `[]`.  

**Example 3**  
Input:  
`nums1 = [0], m = 0, nums2 = [1], n = 1`  
Output:  
`[1]`  
Explanation: Since `m = 0`, `nums1` is empty, and the result is `nums2`.

---

## Solution
The problem can be solved by merging the two arrays in-place. Since `nums1` has enough space to accommodate all elements from both arrays, the solution involves inserting elements from `nums2` into their correct positions in `nums1`.

### Algorithm:
1. Start merging from the end of both arrays, as the largest elements can be placed first in the correct position to avoid overwriting smaller elements.
2. Use three pointers:
   - One for `nums1` starting at index `m-1`.
   - One for `nums2` starting at index `n-1`.
   - One for the end of `nums1` at index `m + n - 1`.
3. Compare the elements from `nums1` and `nums2`, and place the larger element in the position pointed to by the third pointer.
4. If any elements remain in `nums2`, copy them directly into `nums1`.

---

### Code Implementation
```python
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        """
        :type nums1: List[int]
        :type m: int
        :type nums2: List[int]
        :type n: int
        :rtype: None Do not return anything, modify nums1 in-place instead.
        """
        nums1[:]=sorted((nums1[:m]+nums2[:n]))
