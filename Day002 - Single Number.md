# Single Number

Given a  **non-empty** array of integers  `nums`, every element appears  _twice_  except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.


### Example 1: 

**Input:** nums = [2,2,1]
**Output:** 1

### Example 2:

**Input:** nums = [4,1,2,1,2]
**Output:** 4

### Example 3:

**Input:** nums = [1]
**Output:** 1

### **Constraints:**

-   1 <= nums.length <= 3 * 10<sup>4</sup>
-   -3 * 10<sup>4</sup>  <= nums[i] <= 3 * 10<sup>4</sup>
-   Each element in the array appears twice except for one element which appears only once.

## Python Code
### XOR properties: 
- a ^ a = 0
- a ^ 0 = a
- a ^ b = b ^ a
`^` mean XOR operation.

```python
class Solution(object):
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        ans = 0
        for num in nums:
            ans = ans ^ num
        return ans
```

## Solution Walkthrough

- https://www.youtube.com/watch?v=v6s3l3ezNQI

##
## Thank You!
