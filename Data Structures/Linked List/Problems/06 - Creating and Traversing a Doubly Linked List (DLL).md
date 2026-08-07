Creating and Traversing a Doubly Linked List (DLL)

#dsa #java #linkedlist #dll

> **Concept:** [[Doubly Linked List (DLL)]]

## Problem Statement

Create a **Doubly Linked List** in Java, add multiple nodes, and print them in both forward and backward directions.

---

## Code

```java
class Node {
    int data;
    Node prev, next;
    Node(int data) { this.data = data; this.prev = this.next = null; }
}

public class Main {
    public static void main(String[] args) {
        Node head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);

        // Linking forward
        head.next = second;
        second.next = third;

        // Linking backward
        second.prev = head;
        third.prev = second;

        // Forward Traversal
        System.out.print("Forward: ");
        Node current = head;
        Node last = null;
        while (current != null) {
            System.out.print(current.data + " -> ");
            last = current; // Keep track of the last node
            current = current.next;
        }
        System.out.println("null");

        // Backward Traversal (using the last node we found)
        System.out.print("Backward: ");
        while (last != null) {
            System.out.print(last.data + " -> ");
            last = last.prev;
        }
        System.out.println("null");
    }
}
```

---

## Output

```text
Forward: 10 -> 20 -> 30 -> null
Backward: 30 -> 20 -> 10 -> null
```
