# Group Anagram
#Hashtable
- Hint 
	- `ord("a") - ord("a") = 0` create a key that stores this hash logic for all a-z 
	- so each string has unique hash now we just have to compare this hash with other hash
	- If same hash then add to the same hash or make a new one
```
from typing import List

class Solution:
    def igroupAnagrams(self, strs: List[str]) -> List[List[str]]:
        kvp = dict()
        list = []

        for str1 in strs:
            count = [0]*26
            for s in str1:
                count[ord(s)-ord("a")] += 1

            if tuple(count) in kvp:
                kvp[tuple(count)].append(str1)
            else:
                kvp[tuple(count)] = [str1]

        for v in kvp.values():
            list.append(v)

        return list
   
print(Solution().igroupAnagrams(["eat","tea","tan","ate","nat","bat"]))
```
```
Output:
[['eat', 'tea', 'ate'], ['tan', 'nat'], ['bat']]
```

Notes:
- list cannot be directly added to dict as key, need to convert to tuple as tuple is immutable