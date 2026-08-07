Creating a Singly Linked List (SLL)

#dsa #java #linkedlist #sll

> **Concept:** [[Singly Linked List (SLL)]]

## Problem Statement

Create a **Singly Linked List** in Java by defining a `Node` class, creating multiple nodes, linking them together, and displaying the list.

---

## Approach

- Create a `Node` class.
- Create three nodes.
- Assign the first node as the **head**.
- Connect each node using the `next` pointer.
- Traverse the list from the head and print each node.

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
        Node second = new Node(20);
        Node third = new Node(30);

        head.next = second;
        second.next = third;

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
10 -> 20 -> 30 -> null
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Creating Nodes | O(1) |
| Linking Nodes | O(1) |
| Traversing | O(n) |

---

## Key Points

- Each node contains **data** and a **next** reference.
- The first node is called the **head**.
- The last node always points to `null`.
- Traversal starts from the **head**.
- A Singly Linked List can only be traversed in the forward direction.