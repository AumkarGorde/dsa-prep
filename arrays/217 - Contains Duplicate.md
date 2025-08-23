# Contains Duplicate
#Hashtable 

- Hints 
	- Use a hash-set (to store unique keys only)
	- Sort it and check if adjacent element is repeated
```
from typing import List

class Solution:
    def containsDuplicate(self, nums: List[int])-> bool:
        unique = set()
        for num in nums:
            if num in unique:
                return False
            else:
                unique.add(num)
        
        return True
    
print(Solution().containsDuplicate([1,1,1,3,3,4,3,2,4,2]))
```
```
Output:
False
```
