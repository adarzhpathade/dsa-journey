# Singly Linked List (SLL)

#dsa #java #linkedlist #sll

## Formal Definition

A **Singly Linked List (SLL)** is a linear data structure in which each element (called a **node**) contains data and a reference (pointer) to the next node in the sequence, with the last node pointing to `null`.

- **Data** – node mein store ki gayi actual value.
- **Next** – agle node ka memory address/pointer.

---

## Visual Structure

```text
Head
 │
 ▼
+------+-------+     +------+-------+     +------+-------+
| Data | Next  | --> | Data | Next  | --> | Data | Null  |
+------+-------+     +------+-------+     +------+-------+
```

---

## Node Declaration (Java)

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
| `insertAtBeginning()` | List ke starting (Head) par naya node add karta hai. |
| `insertAtEnd()` | List ke end (Tail) par naya node add karta hai. |
| `insertAtPosition()` | Specified position/index par node insert karta hai. |
| `deleteAtBeginning()` | Pehle node (Head) ko remove karta hai. |
| `deleteAtEnd()` | Last node ko remove karta hai. |
| `deleteByValue()` | Specific value wale node ko remove karta hai. |
| `search()` | List mein kisi value ko dhundta hai. |
| `display()` | Saare nodes ko traverse karke print karta hai. |
| `isEmpty()` | Check karta hai kya list empty hai (`head == null`). |
| `size()` | Total nodes ki count return karta hai. |

---

# Advantages (Fayde)

- Dynamic size (runtime par easily scale ho sakta hai).
- Beginning par insertion aur deletion super fast ($O(1)$) hota hai.
- Contiguous memory allocation ki restriction nahi hoti.

---

# Disadvantages (Nuksan)

- Direct indexing ($O(1)$ access) allow nahi karta, sirf sequential traversal ho sakta hai.
- Next pointer store karne ke liye extra memory ki zaroorat hoti hai.
- Traversal sirf aage (forward direction) hi kar sakte hain (backward traverse nahi ho sakta).

---

# Time Complexity

| Operation | Complexity |
|-----------|------------|
| Insert at Beginning | **$O(1)$** |
| Insert at End | **$O(N)$** |
| Insert at Position | **$O(N)$** |
| Delete at Beginning | **$O(1)$** |
| Delete at End | **$O(N)$** |
| Search | **$O(N)$** |
| Traverse (Display) | **$O(N)$** |

---

# Quick Revision (Dhyaan Dene Yagya Baatein)

- Data **Nodes** mein store hota hai.
- Har node mein **Data** aur **Next** pointer hota hai.
- Last node ka Next pointer `null` par point karta hai.
- Memory allocation dynamic hoti hai.
- Sirf forward direction traversal possible hai.
- Random access support nahi hota.