## Problem Description

You are given two integer arrays `nums1` and `nums2`, sorted in non-decreasing order, and two integers `m` and `n`, representing the number of elements in `nums1` and `nums2` respectively.

### Task:
Merge `nums1` and `nums2` into a single array sorted in non-decreasing order.

- The final sorted array should not be returned by the function, but instead be stored inside the array `nums1`. 
- To accommodate this, `nums1` has a length of `m + n`, where:
  - The first `m` elements denote the elements that should be merged.
  - The last `n` elements are set to `0` and should be ignored.  
- `nums2` has a length of `n`.

---

### Example 1:

#### Input:
```plaintext
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6], n = 3

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
        nums1[:] = sorted((nums1[:m] + nums2[:n]))
