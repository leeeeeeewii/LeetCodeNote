https://leetcode-cn.com/problems/qing-wa-tiao-tai-jie-wen-ti-lcof/

### 1. Recursion with track
Store results in a list. **Time O(n) Space O(n)**
```
class Solution:
    def numWays(self, n: int) -> int:
        if n == 0 or n == 1:
            return 1
        res = [1, 1]
        i = 2
        while i <= n:
            res.append(res[i-1]+res[i-2])
            i += 1
        return res[n] % 1000000007
```        

### 2. Dynamic programming
Store previous 2 results. **Time O(n) Space O(1)**
```
class Solution:
    def numWays(self, n: int) -> int:
        a, b = 1, 1
        for i in range(n):
            a, b = b, a+b
        return a % 1000000007
```        
