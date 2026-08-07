Printing a Singly Linked List (SLL)

#dsa #java #linkedlist #sll

> **Concept:** [[Singly Linked List (SLL)]]

## Problem Statement

Print all the elements of a **Singly Linked List** by traversing it from the **head** to the last node.

---

## Approach

- Create a temporary pointer (`current`) and initialize it with `head`.
- Traverse the list until `current` becomes `null`.
- Print the data of each node.
- Move `current` to the next node.

---

## Code

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

Traversal:

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

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Printing / Traversing | O(n) |

---

## Space Complexity

| Complexity |
|------------|
| O(1) |

---

## Key Points

- Traversal always starts from the **head**.
- Continue until `current == null`.
- Every node is visited exactly once.
- Printing a linked list is a traversal operation.