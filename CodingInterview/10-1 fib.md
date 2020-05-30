https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/

### 1. Recursion with track
Store the result in a list. **Time O(n) Space O(n)**
```
class Solution:
    def fib(self, n: int) -> int:
        if n == 0:
            return 0       
        if n == 1:
            return 1
        
        res = [0, 1]
        i = 2
        while i <= n:
            res.append(res[i-1]+res[i-2])
            i += 1
        
        return res[n]%1000000007
```        

### 2. Dynamic programming
Use 2 temporary variables to store previous 2 results. **Time O(n) Space O(1)**
```
class Solution:
    def fib(self, n: int) -> int:        
        res = 0
        res1 = 1
        for i in range(n):
            res1, res = res, res+res1
        
        return res%1000000007
```        
