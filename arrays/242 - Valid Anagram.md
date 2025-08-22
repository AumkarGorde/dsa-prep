# Valid Anagram
- Hints
	- Easily solved by using dictionary
	- Try solving by using one loop instead of 2 loops for w dictionary
	- Can we do it by unicodes ? `ord('A')` 
```
from typing import List

class Solution:
    def isAnagram(self, s: str, t: str)-> bool:
        if s.strip() == "" and t.strip == "":
            return True
        
        if (not s) and (not t):
            return True 

        if len(s) != len(t):
            return False

        unique_pair = dict()
        for _ in s:
            if _ in unique_pair:
                unique_pair[_] += 1
            else:
                unique_pair[_] = 0
        
        for _ in t:
            if _ not in unique_pair:
                return False
            if _ in unique_pair and unique_pair[_] < 0:
                return False
            unique_pair[_] -= 1
        
        print("Its an Anagram")
        return True
        
 

print(Solution().isAnagram("anagram", "nagaram"))

```
```
Output:
Its an Anagram
True
```


## Notes
- `dict.get('a',19)`
	- Gets the value from the dictionary if not present it returns 19