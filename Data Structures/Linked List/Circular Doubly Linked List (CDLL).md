# Circular Doubly Linked List (CDLL)

#dsa #java #linkedlist #cdll

## Formal Definition

A **Circular Doubly Linked List (CDLL)** is a hybrid data structure combining features of Circular and Doubly Linked Lists, where each node has `prev` and `next` pointers, the last node's `next` points to the head, and the head's `prev` points to the last node.

- The **next** pointer of the last node points to the first node (head).
- The **prev** pointer of the first node points to the last node (tail).

---

## Visual Structure

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

## Node Declaration (Java)

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

# Common Operations (Standard Operations)

| Method | Description (Kaam) |
| --------------------- | -------------------------------------------- |
| `insertAtBeginning()` | Head position par naya node add karta hai. |
| `insertAtEnd()` | End (Tail) position par naya node add karta hai. |
| `deleteAtBeginning()` | Pehle node (Head) ko remove karta hai. |
| `deleteAtEnd()` | Last node (Tail) ko remove karta hai. |
| `search()` | List mein key search karta hai. |
| `displayForward()` | Head se Tail ki taraf list print karta hai. |
| `displayBackward()` | Tail se Head ki taraf (reverse) print karta hai. |

---

# Advantages (Fayde)

- Kisi bhi point se bi-directional (forward aur backward) traversal kar sakte hain.
- Head se last node tak turant direct access mil jata hai (`head.prev`).
- Agar sirf `head` pointer maintain karein tab bhi head aur tail dono jagah addition/deletion $O(1)$ constant time mein ho jata hai.
- Fibonacci Heaps jaise complex advanced data structures ke liye ideal structure hai.

---

# Disadvantages (Nuksan)

- Linked lists mein sabse zyaada complex implementation.
- Highest memory overhead (har node mein do pointers `prev` aur `next` lene padte hain).
- Infinite loops aur memory leaks se bachne ke liye pointers handling alert ho kar karni padti hai.

---

# Time Complexity

| Operation | Complexity |
|-----------|------------|
| Insert at Beginning | **$O(1)$** |
| Insert at End | **$O(1)$** |
| Delete at Beginning | **$O(1)$** |
| Delete at End | **$O(1)$** |
| Search | **$O(N)$** |
| Traverse | **$O(N)$** |

---

# Quick Revision (Dhyaan Dene Yagya Baatein)

- Har node mein do pointers hote hain (`prev` aur `next`).
- Last node pehle node se connect hota hai, aur pehla node last node se.
- Head se last element tak instant access `head.prev` ke zariye milta hai.
- Both ends par $O(1)$ insertion aur deletion ops facilitate karta hai.

