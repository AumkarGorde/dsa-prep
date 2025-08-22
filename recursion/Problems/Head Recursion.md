# Head Recursion
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