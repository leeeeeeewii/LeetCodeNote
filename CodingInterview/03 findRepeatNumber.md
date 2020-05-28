https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/

### 1. Sort list
Sort the list, duplicate number would be put together. **Time O(nlogn) Space O(1)**
```
class Solution:
    def findRepeatNumber(self, nums: List[int]) -> int:
        nums.sort()
        for i in range(len(nums)-1):
            if nums[i] == nums[i+1]:
                return nums[i]
```

### 2. Hash table
Store each items of the list, return the duplicate one. **Time O(n) Space O(n)**
```
class Solution:
    def findRepeatNumber(self, nums: List[int]) -> int:
        dic = {}
        for i in nums:
            if i not in dic:
                dic[i] = 1
            else:
                return i
```

### 3. Sort list by swapping values
As 0~n-1 in n-long sorted array, if no duplicate numbers, the value would equal to its index. Hence swap the value *x* and *nums[x]*.  **Time O(n) Space O(1)**
```
class Solution:
    def findRepeatNumber(self, nums: List[int]) -> int:
        for i in range(len(nums)):
            while nums[i] != i:
                if nums[i] == nums[nums[i]]:
                    return nums[i]
                temp = nums[i]
                nums[i], nums[temp] = nums[temp], nums[i]
```
