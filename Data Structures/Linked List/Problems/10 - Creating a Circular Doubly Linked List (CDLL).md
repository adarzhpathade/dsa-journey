Creating a Circular Doubly Linked List (CDLL)

#dsa #java #linkedlist #cdll

> **Concept:** [[Circular Doubly Linked List (CDLL)]]

## Problem Statement

Create a Circular Doubly Linked List where the last node links to the first, and the first node's previous links to the last.

---

## Code

```java
class Node {
    int data;
    Node prev, next;
    Node(int data) { this.data = data; }
}

public class Main {
    public static void main(String[] args) {
        Node head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);

        // Forward links
        head.next = second;
        second.next = third;
        third.next = head; // Last to first

        // Backward links
        head.prev = third; // First to last
        second.prev = head;
        third.prev = second;

        // Traverse forward
        Node current = head;
        System.out.print("Forward: ");
        do {
            System.out.print(current.data + " <-> ");
            current = current.next;
        } while (current != head);
        System.out.println("(Head)");

        // Traverse backward (start from head.prev which is the last node)
        current = head.prev;
        System.out.print("Backward (starting from last): ");
        do {
            System.out.print(current.data + " <-> ");
            current = current.prev;
        } while (current != head.prev);
        System.out.println("(Last)");
    }
}
```

---

## Output

```text
Forward: 10 <-> 20 <-> 30 <-> (Head)
Backward (starting from last): 30 <-> 20 <-> 10 <-> (Last)
```

---

## Key Points

- Notice how easy it is to find the last node (`head.prev`). This makes inserting at the end an $O(1)$ operation without needing a separate `tail` pointer.
