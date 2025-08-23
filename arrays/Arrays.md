# Arrays
### Accessing array elements is constant time O(1)
- Arrays are stored in contiguous memory blocks
- Each element has the same size
- If you know the starting address, you can calculate any element address in memory.

| Index          | 0    | 1    | 2    | 3    | 4    |
| -------------- | ---- | ---- | ---- | ---- | ---- |
| Value          | 12   | 13   | 41   | 215  | 34   |
| Memory Address | 1000 | 1004 | 1008 | 1012 | 1016 |
- Suppose,
	- base - base address 
	- size - size of each element
	- index to access - i
- The memory address of element in `i = 3` is :
	- addr = base + i * size
	- addr = 1000 + 3 * 4 = 1000 + 12 = 1012 

## Problems
1.  [[217 - Contains Duplicate]] 
2. [[242 - Valid Anagram]] 
3. [[1 - Two Sum]]
4. [[49 - Group Anagram]]
5. 