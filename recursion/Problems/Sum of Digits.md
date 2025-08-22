# Sum of Digits
```
  class Solution:
    def addDigits(self, num:int) -> int:
        num = abs(num)
        if num == 0:
            return 0
        return (num % 10) + self.addDigits(num//10)
    
print(Solution().addDigits(256))
```
```
Output:
13
```