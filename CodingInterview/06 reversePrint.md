https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/

### 1. List
Get value orderly from linked list, insert to the front of a new list. **Time O(n) Space O(n)**
```
class Solution:
    def reversePrint(self, head: ListNode) -> List[int]:
        res = []
        while head:
            res.insert(0, head.val)
            head = head.next
        return res
```

### 2. Recursion
Return [] when head == None.**Time O(n) Space O（n)**
```
class Solution:
    def reversePrint(self, head: ListNode) -> List[int]:
        return self.reversePrint(head.next) + [head.val] if head else []
        
```        
