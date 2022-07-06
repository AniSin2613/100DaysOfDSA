# Climbing Stairs

You are climbing a staircase. It takes  `n`  steps to reach the top.

Each time you can either climb  `1`  or  `2`  steps. In how many distinct ways can you climb to the top?


### Example 1: 

**Input:** n = 2

**Output:** 2

**Explanation:** There are two ways to climb to the top.

1. 1 step + 1 step
2. 2 steps

### Example 2:
**Input:** n = 3

**Output:** 3

**Explanation:** There are three ways to climb to the top.

1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step


### **Constraints:**
-   `1 <= n <= 45`


## Python Code

### Approach I : Recursion + Memoization
This can be seen as a recursive problem, where at each step, we need to solve for next two steps:

number of ways at pos 0: *f(0) = f(1) + f(2)*

number of ways at pos 1: *f(1) = f(2) + f(3)*

.. and so on

*=>* *f(i) = f(i+1) + f(i+2)*, while *i* < *n*.

```python
class Solution:
    def climbStairs(self, n: int) -> int:    
        self.computed_dict = {}
        return self.func(0, n)
    
    def func(self, i, n):
        if (i > n):
            return 0
        elif (i == n):
            return 1
        else:
            if (i in self.computed_dict):
                return self.computed_dict[i]
            else:
                self.computed_dict[i] = self.func(i+1, n) + self.func(i+2, n)
                return self.computed_dict[i]
```

### Approach II : Dynamic Programming
The problem is converted into a Fibonacci series if we start solving backward; bottom-up approach for traversing through a tree.

```python
class Solution:
    def climbStairs(self, n: int) -> int:        
        one, two = 1, 1
        
        for i in range(n-1):
            one, two = one+two, one
            
        return one
```

## Solution Walkthrough

- https://www.youtube.com/watch?v=Y0lT9Fck7qI

##
## Thank You!
