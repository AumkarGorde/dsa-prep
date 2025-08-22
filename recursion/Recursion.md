# Recursion
- A function calling itself until a base condition is met
- A case where function does not recur is called a base case
#### Types of recursion
- Tail recursion : recursive call is the last statement
- Head recursion : recursion happens before processing
- Tree recursion :
- Indirect recursion :
- Nested recursion :

### Problems
****
`Factorial of a number`
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
`Fibonacci sequence`
```
class Solution:
    def fib(self, n: int) -> int:
        if n == 0:
            return 0
        if n == 1:
            return 1
        return self.fib(n-1) + self.fib(n-2)

print(Solution().fib(4))
```
```
Output:
3
```
`Sum of digits of a number`
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
`Print numbers from 1 to n - Head recusrion`

```
class Solution:
    def print_num(self, num: int)-> None:
        if num == 0:
            return
        self.print_num(num-1)
        print(num)
    
Solution().print_num(4)
```
```
Output:
1
2
3
4
```
`Print numbers from n to 1 - Tail recursion`
```
class Solution:
    def print_num(self, num: int)-> None:
        if num == 0:
            return
        print(num)
        self.print_num(num-1)
    
Solution().print_num(4)
```
```
Output:
4
3
2
1
```