https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/

### 1. *min* function
**Time O(n) Space O(1)**
```
class Solution:
    def minArray(self, numbers: List[int]) -> int:
        return min(numbers)    
```

### 2. Dichotomy
**Time O(logn) Space O(1)**
```
class Solution:
    def minArray(self, numbers: List[int]) -> int:
        i, j = 0, len(numbers)-1
        while i < j:
            m = (i+j)//2
            if numbers[m] > numbers[j]:
                i = m + 1
            elif numbers[m] < numbers[j]:
                j = m 
            else:
                j -= 1
        return numbers[i]
```        
