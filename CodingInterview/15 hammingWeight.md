https://leetcode-cn.com/problems/er-jin-zhi-zhong-1de-ge-shu-lcof/

### 1. Bitwise operation
**Time O(log2n) Space O(1)**
```
class Solution:
    def hammingWeight(self, n: int) -> int:
        i = 0
        while n:
            i += n & 1
            n >>= 1
        return i
```

### 2. n & (n-1) makes the last one zeros
**O(m) O(1)** m=number of 1
```
class Solution:
    def hammingWeight(self, n: int) -> int:
        # n & (n-1) makes the last one zeros O(m) O(1) m=number of 1
        i = 0
        while n:
            i += 1
            n = n & (n-1)
        return i
```        
