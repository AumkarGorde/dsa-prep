# Factorial
```
class Solution:
    def factorial(self, n: int)->int:
        if n == 1:
            return 1
        if n == 0:
            return 1
        return n * self.factorial(n-1)

print(Solution().factorial(5))
```
```
Output:
120
```