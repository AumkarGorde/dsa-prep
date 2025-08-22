# Tail Recursion
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