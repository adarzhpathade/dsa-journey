#dsa #java #linkedlist #cdll
## Definition

A **Circular Doubly Linked List (CDLL)** combines the features of a Circular Linked List and a Doubly Linked List. 
It has two pointers per node (`prev` and `next`), and it forms a continuous loop:
- The **next** pointer of the last node points to the first node.
- The **prev** pointer of the first node points to the last node.

---

## Structure

```text
     Head
      │
      ▼
    +------+------+-------+     +------+------+-------+     +------+------+-------+
┌─> | Prev | Data | Next  | <-> | Prev | Data | Next  | <-> | Prev | Data | Next  | ─┐
│   +------+------+-------+     +------+------+-------+     +------+------+-------+  │
│     ▲                                                                        ▲     │
│     │                                                                        │     │
└─────┼────────────────────────────────────────────────────────────────────────┼─────┘
      └────────────────────────────────────────────────────────────────────────┘
```

---

## Node Declaration

*(Same as Doubly Linked List)*

```java
class Node {
    int data;
    Node prev;
    Node next;

    Node(int data) {
        this.data = data;
        this.prev = null;
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
| `deleteAtBeginning()` | Removes the first node.                      |
| `deleteAtEnd()`       | Removes the last node.                       |
| `search()`            | Searches for a value in the list.            |
| `displayForward()`    | Traverses nodes from head to tail.           |
| `displayBackward()`   | Traverses nodes from tail to head.           |

---

# Advantages

- Bi-directional traversal from any point.
- Very easy to reach the tail node from the head (just `head.prev`).
- Constant time $O(1)$ operations for adding/removing at both ends if we only maintain a `head` pointer.
- Ideal for complex data structures like Fibonacci Heaps.

---

# Disadvantages

- Most complex implementation of all linked lists.
- Highest memory overhead (two pointers per node).
- Requires careful handling of pointers to avoid infinite loops and memory leaks.

---

# Time Complexity

| Operation | Complexity |
|-----------|------------|
| Insert at Beginning | **O(1)** |
| Insert at End | **O(1)** |
| Delete at Beginning | **O(1)** |
| Delete at End | **O(1)** |
| Search | **O(n)** |
| Traverse | **O(n)** |

---

# Quick Revision

- Two pointers per node (`prev`, `next`).
- Last node connects to the first node, and first node connects to the last node.
- Immediate access to the last element from the head via `head.prev`.
- Allows $O(1)$ insertion and deletion at both ends.
