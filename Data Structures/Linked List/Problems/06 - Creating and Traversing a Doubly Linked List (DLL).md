# Creating and Traversing a Doubly Linked List (DLL)

#dsa #java #linkedlist #dll

> **Concept:** [[Doubly Linked List (DLL)]]

## Problem Statement

Create a **Doubly Linked List** in Java, add multiple nodes, and print them in both forward and backward directions.

---

## Approach (Tarika)

- Node class create karo jisme `prev` aur `next` pointers hon.
- Nodes instantiated karke forward links (`next`) aur backward links (`prev`) dono attach karo.
- Forward traversal: `head` se start karke `current = current.next` moving loops chalao aur `last` node save kar lo.
- Backward traversal: `last` node se start karke `last = last.prev` moving loops se print karo.

---

## Code (Java)

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

        // Forward linking (next pointers)
        head.next = second;
        second.next = third;

        // Backward linking (prev pointers)
        second.prev = head;
        third.prev = second;

        // Forward Traversal
        System.out.print("Forward: ");
        Node current = head;
        Node last = null;
        while (current != null) {
            System.out.print(current.data + " -> ");
            last = current; // Last node track karne ke liye
            current = current.next;
        }
        System.out.println("null");

        // Backward Traversal (Last node se piche aao)
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

