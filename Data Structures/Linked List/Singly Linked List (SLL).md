#dsa #java #linkedlist #sll
## Definition

A **Singly Linked List (SLL)** is a linear data structure in which each element (called a **node**) contains:

- **Data** – the value stored in the node.
- **Next** – a reference (pointer) to the next node.

The last node points to `null`.

---

## Structure

```text
Head
 │
 ▼
+------+-------+     +------+-------+     +------+-------+
| Data | Next  | --> | Data | Next  | --> | Data | Null  |
+------+-------+     +------+-------+     +------+-------+
```

---

## Node Declaration

```java
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}
```

---

# Common Operations

| Method                | Description                                  |
| --------------------- | -------------------------------------------- |
| `insertAtBeginning()` | Inserts a node at the beginning of the list. |
| `insertAtEnd()`       | Inserts a node at the end of the list.       |
| `insertAtPosition()`  | Inserts a node at a specified position.      |
| `deleteAtBeginning()` | Removes the first node.                      |
| `deleteAtEnd()`       | Removes the last node.                       |
| `deleteByValue()`     | Removes the node with the specified value.   |
| `search()`            | Searches for a value in the list.            |
| `display()`           | Traverses and prints all nodes.              |
| `isEmpty()`           | Checks whether the list is empty.            |
| `size()`              | Returns the number of nodes in the list.     |

---

# Advantages

- Dynamic size (can grow or shrink at runtime).
- Efficient insertion and deletion at the beginning.
- Does not require contiguous memory.

---

# Disadvantages

- Sequential access only (no direct indexing).
- Extra memory required for storing pointers.
- Traversal is only in the forward direction.

---

# Time Complexity

| Operation | Complexity |
|-----------|------------|
| Insert at Beginning | **O(1)** |
| Insert at End | **O(n)** |
| Insert at Position | **O(n)** |
| Delete at Beginning | **O(1)** |
| Delete at End | **O(n)** |
| Search | **O(n)** |
| Traverse (Display) | **O(n)** |

---

# Quick Revision

- Stores data in **nodes**.
- Each node contains **data** and a **next** pointer.
- Last node points to `null`.
- Dynamic memory allocation.
- Forward traversal only.
- No random access.