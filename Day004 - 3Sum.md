# 3Sum


Given an integer array nums, return all the triplets  `[nums[i], nums[j], nums[k]]`  such that  `i != j`,  `i != k`, and  `j != k`, and  `nums[i] + nums[j] + nums[k] == 0`.

Notice that the solution set must not contain duplicate triplets.


### Example 1: 
**Input:** nums = [-1,0,1,2,-1,-4]
**Output:** [[-1,-1,2],[-1,0,1]]

### Example 2:
**Input:** nums = []
**Output:** []

### Example 3:
**Input:** nums = [0]
**Output:** []

### **Constraints:**
-   0 <= nums.length <= 3000
-   -10<sup>5</sup>  <= nums[i] <= 10<sup>5</sup>

## Python Code
### CurrentValue + TwoSum_II

```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        nums.sort()
        result = []
        
        for i,a in enumerate(nums):
            if i>0 and a==nums[i-1]:
                continue
                
            left, right = i+1, len(nums)-1
            
            while left < right:
                threeSum = a + nums[left] + nums[right]
                if threeSum < 0:
                    left += 1
                elif threeSum > 0:
                    right -= 1
                else:
                    result.append([a, nums[left], nums[right]])
                    left += 1
                    while (nums[left] == nums[left - 1]) and (left < right):
                        left += 1
        return result
```

## Solution Walkthrough

- https://www.youtube.com/watch?v=jzZsG8n2R9A

##
## Thank You!
