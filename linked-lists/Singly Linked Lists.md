# Singly Linked Lists
- The elements are connected sequentially
- Each node consists of
	- data - value stored in node
	- next pointer - a reference to the next node in the sequence
- The first node is the head
- The last node pointer is NULL, indicating the end of the list
- Traversal is one way - forward only 

### Basic operations
- Traversal - visit each node starting from the head
- Insertion - Adding a node at :
	- Beginning 
	- End 
	- Specific position
- Deletion - Remove node from
	- Beginning 
	- End
	- Specific position 
- Searching - Find if value exist in the list

### Traverse
- Create Nodes
- Join the nodes
- Traverse nodes
- Time Complexity: O(n)
	- For scanning the list on n size O(n)
- Space Complexity: O(1)
```
from __future__ import annotations
from typing import Optional

class Node:
    def __init__(self, data: int, next: Optional[Node] = None) -> None:
        self.data: int = data
        self.next: Optional[Node] = None

n1 = Node(1)
n1.next = Node(2)
n1.next.next = Node(3)
n1.next.next.next = Node(4)

def traverse(head:Node):
    while head is not None:
        print(f"{head.data} -> ", end="")
        head = head.next

    print("Traverse complete")

traverse(n1)
```
```
Output:
1 -> 2 -> 3 -> 4 -> Traverse complete
```
### Insertion node at beginning
 - Time Complexity : O(1)
	 - create new node : O(1)
	 - Point next to current head : O(1)
- Space Complexity : O(1)
	- For insertion operation no new data structure or array is used
```
from __future__ import annotations
from typing import Optional

class Node:
    def __init__(self, data: int, next: Optional[Node] = None) -> None:
        self.data: int = data
        self.next: Optional[Node] = None

n1 = Node(1)
n1.next = Node(2)
n1.next.next = Node(3)
n1.next.next.next = Node(4)

def add_at_start(new_node:Node, old_node: Node):
    new_node.next = old_node


def traverse(head:Node):
    while head is not None:
        print(f"{head.data} -> ", end="")
        head = head.next

    print("Traverse complete")

traverse(n1)
print("----------------------")
new_node = Node(0)
add_at_start(new_node, n1)
traverse(new_node)

```
### Insertion node at end
- Time Complexity : O(n)
	- Traverse the whole node: O(n)
	- Put the new node at the last
- Space Complexity : O(1)
	- For insertion operation no new data structure or array is used
```
from __future__ import annotations
from typing import Optional

class Node:
    def __init__(self,data: int, next: Optional[None] = None) -> None:
        self.data:int = data
        self.next:Optional[Node] = None

n1 = Node(1)
n1.next = Node(2)
n1.next.next = Node(3)
n1.next.next.next = Node(4)

def add_at_end(new_node:Node, n1:Node)-> None:
    while n1.next is not None:
        n1 = n1.next
    
    n1.next = new_node

def traverse(n1:Node)-> None:
    while n1 is not None:
        print(f"{n1.data} -> ", end="")
        n1 = n1.next 

    print("Complete") 

traverse(n1)
new_node = Node(5)
add_at_end(new_node, n1)
traverse(n1)
```
```
Output:
1 -> 2 -> 3 -> 4 -> Complete
1 -> 2 -> 3 -> 4 -> 5 -> Complete
```
### Inserstion of node at a position
- Time Complexity O(n). 
	- In worst case we might require to loop the entire list
- Space Complexity O(1)
📝 Below code need to be updated to handle pos=0, invalid pos, and last pos
```
from __future__ import annotations
from typing import Optional

class Node:
    def __init__(self,data: int, next: Optional[None] = None) -> None:
        self.data:int = data
        self.next:Optional[Node] = None

n1 = Node(1)
n1.next = Node(2)
n1.next.next = Node(4)
n1.next.next.next = Node(5)

def add_at_given_point(new_node:Node, n1:Node, ins_pos: int)-> None:
    curr = n1
    for p in range(1, ins_pos-1):
        if(curr is None):
            break
        curr = curr.next
    
    new_node.next = curr.next
    curr.next = new_node

def traverse(n1:Node)-> None:
    while n1 is not None:
        print(f"{n1.data} -> ", end="")
        n1 = n1.next 

    print("Complete") 

traverse(n1)
new_node = Node(3)
add_at_given_point(new_node, n1, 3)
traverse(n1)
```
```
Output: 
1 -> 2 -> 4 -> 5 -> Complete
1 -> 2 -> 3 -> 4 -> 5 -> Complete
```

### Delete the first node
- Time Complexity: O(1)
- Space Complexity: O(1)
	- Memory usage does not grows in increase list
```
from __future__ import annotations
from typing import Optional

class Node:
    def __init__(self,data: int, next: Optional[None] = None) -> None:
        self.data:int = data
        self.next:Optional[Node] = None

n1 = Node(1)
n1.next = Node(2)
n1.next.next = Node(3)
n1.next.next.next = Node(4)

def traverse(n1:Node)-> None:
    while n1 is not None:
        print(f"{n1.data} -> ", end="")
        n1 = n1.next 

    print("Complete") 


def delete_at_start(head:Node)-> Node:
    temp = head
    new_head = head.next
    del temp
    return new_head

traverse(n1)
n2 = delete_at_start(n1)
traverse(n2)
```
```
Output:
1 -> 2 -> 3 -> 4 -> Complete
2 -> 3 -> 4 -> Complete
```
### Delete the last node
- Time Complexity: O(n)
	- Scan the whole list to go at the end
- Space Complexity: O(1)
```
from __future__ import annotations
from typing import Optional

class Node:
    def __init__(self,data: int, next: Optional[None] = None) -> None:
        self.data:int = data
        self.next:Optional[Node] = None

n1 = Node(1)
n1.next = Node(2)
n1.next.next = Node(3)
n1.next.next.next = Node(4)

def traverse(n1:Node)-> None:
    while n1 is not None:
        print(f"{n1.data} -> ", end="")
        n1 = n1.next 

    print("Complete") 


def delete_at_end(head:Node)-> Node:
    second_last = head
    while second_last.next.next is not None:
        second_last = second_last.next

    second_last.next = None
    return head

traverse(n1)
n2 = delete_at_end(n1)
traverse(n2)
```
```
Output:
1 -> 2 -> 3 -> 4 -> Complete
1 -> 2 -> 3 -> Complete
```
### Delete a node at a position
- Time complexity: O(n)
	- In worst case you might need to traverse entire loop
- Space Complexity: O(1)
```
from __future__ import annotations
from typing import Optional

class Node:
    def __init__(self,data: int, next: Optional[None] = None) -> None:
        self.data:int = data
        self.next:Optional[Node] = None

n1 = Node(1)
n1.next = Node(2)
n1.next.next = Node(3)
n1.next.next.next = Node(4)

def traverse(n1:Node)-> None:
    while n1 is not None:
        print(f"{n1.data} -> ", end="")
        n1 = n1.next 

    print("Complete") 


def delete_at_pos(head:Node, pos:int)-> Node:
    curr = head
    for _ in range(1,pos-1):
        curr = curr.next

    curr.next = curr.next.next
    return head

traverse(n1)
n2 = delete_at_pos(n1,3)
traverse(n2)
```
```
Output: 
1 -> 2 -> 3 -> 4 -> Complete
1 -> 2 -> 4 -> Complete
```
### Deleting a linked list
- Time Complexity : O(n)
- Space Complexity : O(1)
```
from __future__ import annotations
from typing import Optional

class Node:
    def __init__(self,data: int, next: Optional[None] = None) -> None:
        self.data:int = data
        self.next:Optional[Node] = None

n1 = Node(1)
n1.next = Node(2)
n1.next.next = Node(3)
n1.next.next.next = Node(4)

def traverse(n1:Node)-> None:
    while n1 is not None:
        print(f"{n1.data} -> ", end="")
        n1 = n1.next 

    print("Complete") 


def delete(head:Node)-> Node:
    curr = head
    while curr is not None:
        next_node = curr.next
        curr.next = None
        curr = next_node
    return None 

traverse(n1)
n1 = delete(n1)
print(n1)
```
```
Output:
1 -> 2 -> 3 -> 4 -> Complete
None
```