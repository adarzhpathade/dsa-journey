# Doubly Linked List (DLL)

#dsa #java #linkedlist #dll

## Formal Definition

A **Doubly Linked List (DLL)** is a linear data structure in which each element (called a **node**) contains three parts:
- **Prev** – a reference (pointer) to the previous node.
- **Data** – the value stored in the node.
- **Next** – a reference (pointer) to the next node.

The first node's `prev` and the last node's `next` point to `null`.

---

## Visual Structure

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

*(Note: First node ka Prev Null hota hai, aur last node ka Next Null hota hai)*

---

## Node Declaration (Java)

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
| `insertAtBeginning()` | Head par naya node add karta hai. |
| `insertAtEnd()` | Tail (end) par naya node add karta hai. |
| `insertAtPosition()` | Specified position par node insert karta hai. |
| `deleteAtBeginning()` | Pehle node ko remove karta hai. |
| `deleteAtEnd()` | Last node ko remove karta hai. |
| `deleteByValue()` | Specific value wale node ko delete karta hai. |
| `search()` | List mein target element search karta hai. |
| `displayForward()` | Head se Tail ki taraf nodes print karta hai. |
| `displayBackward()` | Tail se Head ki taraf (reverse) print karta hai. |

---

# Advantages (Fayde)

- List ko forward aur backward (dono directions mein) traverse kar sakte hain.
- Deletion efficient hota hai agar deleted node ka reference directly diya gaya ho (pichle node par traverse karne ki zaroorat nahi padti).
- Given node se pehle naya node insert karna SLL ke comparison mein continuous pointer update se easily ho jata hai.

---

# Disadvantages (Nuksan)

- Each node mein extra `prev` pointer store karne se memory overhead badh jata hai.
- Implementation thodi complex hai (insertion/deletion ke waqt do pointers update karne padte hain).
- Random access ($O(1)$ direct index access) support nahi karta.

---

# Time Complexity

| Operation | Complexity |
|-----------|------------|
| Insert at Beginning | **$O(1)$** |
| Insert at End | **$O(1)$** *(agar tail pointer maintaned ho)* ya **$O(N)$** |
| Insert at Position | **$O(N)$** |
| Delete at Beginning | **$O(1)$** |
| Delete at End | **$O(1)$** *(agar tail pointer maintaned ho)* ya **$O(N)$** |
| Search | **$O(N)$** |
| Traverse | **$O(N)$** |

---

# Quick Revision (Dhyaan Dene Yagya Baatein)

- Data **Nodes** mein store hota hai.
- Node structure: **prev**, **data**, aur **next** pointers.
- Bidirectional traversal (Aage aur Peeche dono taraf traverse kar sakte hain).
- SLL ke comparison mein memory overhead thoda zyaada hota hai.
- Target node pointer pata ho toh deletion $O(1)$ ho jata hai.

