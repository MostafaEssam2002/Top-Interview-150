## Problem Description

Given an integer array `nums` and an integer `val`, remove all occurrences of `val` from `nums` **in-place**. The order of the elements may be changed. Then return the number of elements in `nums` which are not equal to `val`.

### Requirements:
1. Modify the array `nums` such that the first `k` elements contain the elements which are not equal to `val`.
2. The remaining elements in `nums` beyond the first `k` are not important.
3. Return `k` (the count of elements not equal to `val`).

---

### Examples
**Example 1**  
Input:  
`nums = [3,2,2,3], val = 3`  
Output:  
`k = 2, nums = [2,2,_,_]`  
Explanation: The first two elements of `nums` are `2`. The order does not matter.

**Example 2**  
Input:  
`nums = [0,1,2,2,3,0,4,2], val = 2`  
Output:  
`k = 5, nums = [0,1,4,0,3,_,_,_]`  
Explanation: The first five elements of `nums` are `[0, 1, 4, 0, 3]`. The order does not matter.

---

## Solution
The solution uses a pointer `k` to track where the next non-`val` element should be placed. By iterating through `nums` and checking each element, we overwrite values equal to `val` while keeping other values in place.

### Algorithm:
1. Initialize `k = 0` as the position where the next non-`val` element will be stored.
2. Iterate through the array:
   - If the current element is not equal to `val`, move it to index `k` and increment `k`.
3. After completing the loop, `k` will hold the count of elements not equal to `val`, and the array will be modified in-place.
4. Return `k`.

---

### Code Implementation
```python
class Solution(object):
    def removeElement(self, nums, val):
        """
        :type nums: List[int]
        :type val: int
        :rtype: int
        """
        k = 0  # Pointer to the position for non-val elements
        for i in range(len(nums)):
            if nums[i] != val:
                nums[k] = nums[i]  # Move the non-val element to index k
                k += 1  # Increment k for the next position
        return k
