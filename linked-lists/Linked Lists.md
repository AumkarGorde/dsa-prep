# Linked Lists

`A  linked list is a data structure that consist of nodes, where each node contains a data and a reference pointer to the next node `
- Entry point to linked list is called as head
- If list is empty the head is null refrence
- 
### Types of linked list 
- Singly Linked list - nodes point only to the next node
- Doubly linked list - node point to both next and previous nodes
- Circular linked list : last node points back to the first node
### Advantage of linked lists over array
- Dynamic size : can grow and shrink at runtime
- Efficient insertions and deletion - especially at the beginning and at the end

### Disadvantage of a linked list
- No direct access to the elements it is sequential access only
- Uses extra memory for pointers

## Singly Linked List
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
