# Creating a Circular Doubly Linked List (CDLL)

#dsa #java #linkedlist #cdll

> **Concept:** [[Circular Doubly Linked List (CDLL)]]

## Problem Statement

Create a Circular Doubly Linked List where the last node links to the first, and the first node's previous links to the last.

---

## Code (Java)

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

        // Forward links (next pointers)
        head.next = second;
        second.next = third;
        third.next = head; // Last node se first node link

        // Backward links (prev pointers)
        head.prev = third; // First node se last node link
        second.prev = head;
        third.prev = second;

        // Forward Traversal
        Node current = head;
        System.out.print("Forward: ");
        do {
            System.out.print(current.data + " <-> ");
            current = current.next;
        } while (current != head);
        System.out.println("(Head)");

        // Backward Traversal (Last node head.prev se start karke reverse aao)
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

## Key Points (Khaas Baatein)

- Dhyaan do ki `head.prev` ka use karke last node kitna easily access ho jata hai. Is wajah se bina separate `tail` pointer rakhe end mein insertion $O(1)$ constant time operation ban jata hai.

