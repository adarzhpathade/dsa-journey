#dsa #java #linkedlist #dll
## Definition

A **Doubly Linked List (DLL)** is a linear data structure in which each element (called a **node**) contains three parts:

- **Prev** – a reference (pointer) to the previous node.
- **Data** – the value stored in the node.
- **Next** – a reference (pointer) to the next node.

The first node's `prev` and the last node's `next` point to `null`.

---

## Structure

```text
 Null        Head                                              Null
  ▲           │                                                 ▲
  │           ▼                                                 │
+------+------+-------+     +------+------+-------+     +------+------+-------+
| Prev | Data | Next  | <-> | Prev | Data | Next  | <-> | Prev | Data | Next  |
+------+------+-------+     +------+------+-------+     +------+------+-------+
  │                                                             │
  ▼                                                             ▼
 Null                                                          Null
```

*(Note: The first node's Prev is Null, and the last node's Next is Null)*

---

## Node Declaration

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
| `insertAtPosition()`  | Inserts a node at a specified position.      |
| `deleteAtBeginning()` | Removes the first node.                      |
| `deleteAtEnd()`       | Removes the last node.                       |
| `deleteByValue()`     | Removes the node with the specified value.   |
| `search()`            | Searches for a value in the list.            |
| `displayForward()`    | Traverses and prints nodes from head to tail.|
| `displayBackward()`   | Traverses and prints nodes from tail to head.|

---

# Advantages

- Can be traversed in both forward and backward directions.
- Deletion is more efficient if the node to be deleted is given (no need to traverse to find the previous node).
- Inserting a node before a given node is easier compared to a Singly Linked List.

---

# Disadvantages

- Extra memory is required for storing the `prev` pointer in each node.
- More complex implementation (need to manage two pointers during insertion/deletion).
- Still no direct indexing (random access).

---

# Time Complexity

| Operation | Complexity |
|-----------|------------|
| Insert at Beginning | **O(1)** |
| Insert at End | **O(1)** *(if tail pointer exists)* or **O(n)** |
| Insert at Position | **O(n)** |
| Delete at Beginning | **O(1)** |
| Delete at End | **O(1)** *(if tail pointer exists)* or **O(n)** |
| Search | **O(n)** |
| Traverse | **O(n)** |

---

# Quick Revision

- Stores data in **nodes**.
- Each node contains **data**, a **prev** pointer, and a **next** pointer.
- Bidirectional traversal (forward and backward).
- Higher memory overhead per node than SLL.
- Deleting a known node is O(1).
