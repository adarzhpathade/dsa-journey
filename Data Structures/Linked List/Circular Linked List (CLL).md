#dsa #java #linkedlist #cll
## Definition

A **Circular Linked List (CLL)** is a variation of a linked list in which the first element points to the second element and so on, but the **last element points back to the first element (head)**. It forms a continuous loop.

It can be either a Singly Circular Linked List or a Doubly Circular Linked List. By default, it usually refers to the singly linked variation.

---

## Structure

```text
     Head
      │
      ▼
    +------+-------+     +------+-------+     +------+-------+
┌─> | Data | Next  | --> | Data | Next  | --> | Data | Next  | ─┐
│   +------+-------+     +------+-------+     +------+-------+  │
│                                                               │
└───────────────────────────────────────────────────────────────┘
```

---

## Node Declaration

*(Same as Singly Linked List)*

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
| `deleteAtBeginning()` | Removes the first node.                      |
| `deleteAtEnd()`       | Removes the last node.                       |
| `search()`            | Searches for a value in the list.            |
| `display()`           | Traverses and prints all nodes until the head is reached again. |

---

# Advantages

- Any node can be a starting point. We can traverse the whole list by starting from any node.
- Useful for implementing round-robin scheduling algorithms or multiplayer games (e.g., turn-based).
- Can avoid the `null` check at the end.

---

# Disadvantages

- Complex implementation (you must be careful to avoid infinite loops during traversal).
- If not handled properly, code can run infinitely since there is no `null` terminator.

---

# Time Complexity

| Operation | Complexity |
|-----------|------------|
| Insert at Beginning | **O(n)** *(must update last node's next)* or **O(1)** *(if tail pointer kept)* |
| Insert at End | **O(n)** or **O(1)** *(if tail pointer kept)* |
| Delete at Beginning | **O(n)** or **O(1)** *(if tail pointer kept)* |
| Delete at End | **O(n)** |
| Search | **O(n)** |
| Traverse | **O(n)** |

---

# Quick Revision

- The last node points back to the **first node**.
- Forms a closed loop (no `null` pointers).
- Can traverse the entire list starting from *any* node.
- Great for repetitive, cyclical tasks (like a media player playlist loop).
