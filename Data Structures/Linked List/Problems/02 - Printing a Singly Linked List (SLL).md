# Printing a Singly Linked List (SLL)

#dsa #java #linkedlist #sll

> **Concept:** [[Singly Linked List (SLL)]]

## Problem Statement

Print all the elements of a **Singly Linked List** by traversing it from the **head** to the last node.

---

## Approach (Tarika)

- Ek temporary pointer (`current`) banao aur ise `head` se initialize karo.
- Tab tak list traverse karo jab tak `current` pointer `null` na ho jaye.
- Har node ka data print karo.
- `current` pointer ko agle node par move (`current = current.next`) karo.

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
        head.next = new Node(20);
        head.next.next = new Node(30);

        printList(head);
    }

    static void printList(Node head) {

        Node current = head;

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

Step-by-step Traversal:

```text
current = head

Print 10
      │
      ▼
Print 20
      │
      ▼
Print 30
      │
      ▼
null (Stop)
```

---

## Time & Space Complexity

| Operation | Complexity |
|-----------|------------|
| Printing / Traversing | $O(N)$ |
| Auxiliary Space | $O(1)$ |

---

## Key Points (Khaas Baatein)

- Traversal hamesha **head** node se start hoti hai.
- Loop tab tak chalta hai jab tak `current == null` na ho jaye.
- Har node exact ek baar visit hota hai.
- Linked list ko print karna Basically ek traversal operation hi hai.