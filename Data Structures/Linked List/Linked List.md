# Linked List

#dsa #java #linkedlist 

## Formal Definition

A **Linked List** is a linear data structure in which elements (called **nodes**) are stored **non-contiguously** in memory. Each node contains **data** and one or more **references (links)** to other nodes, allowing dynamic memory allocation and efficient insertion/deletion operations.

Unlike arrays, linked lists do not require contiguous memory, making them flexible for dynamic data storage.

---

## Structure of a Node (Java)

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

## Visual Representation

```text
Head
 ↓
10 → 20 → 30 → 40 → null
```

---

## Key Characteristics

- Dynamic size (runtime par badh ya ghat sakta hai).
- Nodes memory mein non-contiguous (alag-alag bikhri) locations par hote hain.
- Har node data aur agle node ka memory reference (link) hold karta hai.
- Sequential access only (array ki tarah direct indexing `arr[i]` support nahi karta).
- Insertion aur deletion operations arrays ke comparison mein efficient ($O(1)$ at head) hote hain.

---

## Types of Linked List

- [[Singly Linked List (SLL)]]
- [[Doubly Linked List (DLL)]]
- [[Circular Linked List (CLL)]]
- [[Circular Doubly Linked List (CDLL)]]

---

## Advantages (Fayde)

- Dynamic memory allocation (size pre-define nahi karna padta).
- Head/Tail par fast insertion aur deletion operations.
- Fixed capacity na hone se zero memory wastage.
- Stacks aur Queues jaise dynamic data structures implement karna aasan.

---

## Disadvantages (Nuksan)

- Random access nahi hota (nth element par jaane ke liye traverse karna padta hai).
- Pointers store karne ke liye extra memory ki zaroorat hoti hai.
- Non-contiguous memory ki wajah se arrays jitna cache-friendly nahi hota.

---

## Real-World Applications

- Stack aur Queue implementation
- Browser History (Forward/Back navigation)
- Undo/Redo Operations in text editors
- Music Playlist (Next/Previous song)
- Hash Tables (Separate Chaining for collisions)
- Graph Representation (Adjacency List)
- LRU Cache