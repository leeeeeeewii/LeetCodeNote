https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/

### 1. Brute force with judgement
Check line by line if the fisrt value of the line is not greater than target. **Time O(mn) Space O(1)**
```
class Solution:
    def findNumberIn2DArray(self, matrix: List[List[int]], target: int) -> bool:
        if not matrix or not matrix[0]:
            return False

        n, m = len(matrix), len(matrix[0])
        
        for i in range(n):
            if target < matrix[i][0]:
                return False
            elif target > matrix[i][m-1]:
                continue
            else:
                if target in matrix[i]:
                    return True

        return False
```

### 2. Binary tree search
Start from the right-top number, go left if greater than target, go right if smaller than target. **Time O(m+n) Space O(1)**
```
class Solution:
    def findNumberIn2DArray(self, matrix: List[List[int]], target: int) -> bool:
        if not matrix or not matrix[0]:
            return False

        n, m = len(matrix), len(matrix[0])
        
        i, j = n-1, 0
        
        while i >=0 and j < m:
            if matrix[i][j] == target:
                return True
            elif matrix[i][j] > target:
                i -= 1
            else:
                j += 1

        return False
```
