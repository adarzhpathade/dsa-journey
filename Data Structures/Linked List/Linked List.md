#dsa #java #linkedlist 


A **Linked List** is a linear data structure in which elements (called **nodes**) are stored **non-contiguously** in memory. Each node contains **data** and one or more **references (links)** to other nodes, allowing dynamic memory allocation and efficient insertion/deletion operations.

Unlike arrays, linked lists do not require contiguous memory, making them flexible for dynamic data storage.

---

## Structure of a Node

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

## Representation

```text
Head
 ↓
10 → 20 → 30 → 40 → null
```

---

## Characteristics

- Dynamic size (can grow or shrink during runtime)
- Nodes are stored in non-contiguous memory locations.
- Each node contains data and a reference to the next node.
- Sequential access only (no direct indexing).
- Efficient insertion and deletion compared to arrays.

---

## Types of Linked List

- [[Singly Linked List (SLL)]]
- [[Doubly Linked List (DLL)]]
- [[Circular Linked List (CLL)]]
- [[Circular Doubly Linked List (CDLL)]]

---

## Advantages

- Dynamic memory allocation.
- Fast insertion and deletion operations.
- No memory wastage due to fixed size.
- Easy implementation of dynamic data structures like stacks and queues.

---

## Disadvantages

- No random access to elements.
- Extra memory required for storing pointers.
- Traversal is slower than arrays due to sequential access.

---

## Applications

- Stack
- Queue
- Browser History
- Undo/Redo Operations
- Music Playlist
- Hash Tables (Separate Chaining)
- Graph Representation
- LRU Cache