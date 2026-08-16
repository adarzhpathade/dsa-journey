# Creating a Singly Linked List (SLL)

#dsa #java #linkedlist #sll

> **Concept:** [[Singly Linked List (SLL)]]

## Problem Statement

Create a **Singly Linked List** in Java by defining a `Node` class, creating multiple nodes, linking them together, and displaying the list.

---

## Approach (Tarika)

- Ek `Node` class create karo (`data` aur `next` fields ke saath).
- Teen distinct nodes instantiate karo.
- Pehle node ko **head** assign karo.
- `next` pointer ka use karke har node ko agle node se link karo.
- Head se traversal shuru karo aur har node ka data print karo jab tak `null` na aa jaye.

---

## Code (Java)

```java
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class Main {

    public static void main(String[] args) {

        Node head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);

        // Nodes ko link karna
        head.next = second;
        second.next = third;

        Node current = head;

        // Traversal loop
        while (current != null) {
            System.out.print(current.data + " -> ");
            current = current.next;
        }

        System.out.println("null");
    }
}
```

---

## Output

```text
10 -> 20 -> 30 -> null
```

---

## Dry Run

```text
Head
 │
 ▼
[10 | • ] ───► [20 | • ] ───► [30 | null]
```

Traversal step-by-step:

```text
10 -> 20 -> 30 -> null
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Creating Nodes | $O(1)$ |
| Linking Nodes | $O(1)$ |
| Traversing | $O(N)$ |

---

## Key Points (Khaas Baatein)

- Har node mein **data** aur **next** reference (link) hota hai.
- Pehle node ko **head** pointer refer karta hai.
- List ka last node hamesha `null` par point karta hai.
- Traversal hamesha **head** se hi start hoti hai.
- Singly Linked List mein traversal sirf forward direction mein hi ho sakti hai.