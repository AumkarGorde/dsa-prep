# Two Sum
#Prefixsum
- Hints 
	- target - n = diff and this diff should be in dictionary with its in index
	- check for adding duplicate keys to the same dic
```
from typing import List

class Solution:
    def twoSum(self, nums : List[int], target: int) -> List[int]:
        kvp = {}
        for i in range(0,len(nums)):
            res = target - nums[i]
            if nums[i] in kvp:
                return [kvp[nums[i]], i]
            else:
                if res not in kvp:
                    kvp[res] = i
        return []
    
print(Solution().twoSum([9,7,11,2], 9))
```
```
Output:
[1, 3]
```