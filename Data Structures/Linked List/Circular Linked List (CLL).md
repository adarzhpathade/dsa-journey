# Circular Linked List (CLL)

#dsa #java #linkedlist #cll

## Formal Definition

A **Circular Linked List (CLL)** is a variation of a linked list in which all nodes are connected in a continuous circle, where the **last node's `next` pointer points back to the first node (head)** instead of `null`.

It can be either a Singly Circular Linked List or a Doubly Circular Linked List. By default, it usually refers to the singly linked variation.

---

## Visual Structure

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

## Node Declaration (Java)

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

# Common Operations (Standard Operations)

| Method | Description (Kaam) |
| --------------------- | -------------------------------------------- |
| `insertAtBeginning()` | List ke Head position par naya node add karta hai. |
| `insertAtEnd()` | List ke End (Tail) par naya node add karta hai. |
| `deleteAtBeginning()` | Pehla node (Head) remove karta hai. |
| `deleteAtEnd()` | Last node remove karta hai. |
| `search()` | Target value ko search karta hai. |
| `display()` | Head se shuru karke wapas Head aane tak sabhi nodes print karta hai. |

---

# Advantages (Fayde)

- Kisi bhi node se starting karke poori list ko traverse kiya ja sakta hai.
- Round-robin scheduling algorithms ya turn-based multiplayer games ke liye extremely useful hai.
- End mein `null` check karne ki requirement nahi hoti.

---

# Disadvantages (Nuksan)

- Implementation thodi complex hoti hai (traversal ke waqt infinite loop se bachna padta hai).
- Sahi condition na lagane par code infinitely run kar sakta hai kyunki ending point mein `null` pointer nahi hota.

---

# Time Complexity

| Operation | Complexity |
|-----------|------------|
| Insert at Beginning | **$O(N)$** *(last node ka next update karna padta hai)* ya **$O(1)$** *(agar tail pointer rakha ho)* |
| Insert at End | **$O(N)$** ya **$O(1)$** *(agar tail pointer rakha ho)* |
| Delete at Beginning | **$O(N)$** ya **$O(1)$** *(agar tail pointer rakha ho)* |
| Delete at End | **$O(N)$** |
| Search | **$O(N)$** |
| Traverse | **$O(N)$** |

---

# Quick Revision (Dhyaan Dene Yagya Baatein)

- Last node ka Next pointer **first node (head)** par point karta hai.
- Closed loop banata hai (koi `null` pointer nahi hota).
- Kisi bhi random node se start karke poori list traverse kar sakte hain.
- Repetitive cyclic tasks (jaise playlist loop) ke liye perfect hai.

