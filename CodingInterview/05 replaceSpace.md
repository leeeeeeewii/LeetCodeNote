https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/

### 1. *replace* function
**Time O(n) Space O(1)**
```
class Solution:
    def replaceSpace(self, s: str) -> str:
        return s.replace(' ', '%20')
```        

### 2. List
Loop to check every items in string, insert into list, convert list to a string. **Time O(n) Space O(n)**
```
class Solution:
    def replaceSpace(self, s: str) -> str:
        res = []
        for i in s:
            if i == ' ': 
              res.append("%20")
            else: 
              res.append(i)
        return "".join(res)
```
