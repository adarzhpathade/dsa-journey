Creating and Traversing a Circular Linked List (CLL)

#dsa #java #linkedlist #cll

> **Concept:** [[Circular Linked List (CLL)]]

## Problem Statement

Create a Circular Linked List and traverse it until it reaches the head again.

---

## Code

```java
class Node {
    int data;
    Node next;
    Node(int data) { this.data = data; }
}

public class Main {
    public static void main(String[] args) {
        Node head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);

        head.next = second;
        second.next = third;
        // Make it circular by connecting the last node to the head
        third.next = head; 

        // Traversal
        if (head != null) {
            Node current = head;
            do {
                System.out.print(current.data + " -> ");
                current = current.next;
            } while (current != head); // Stop when we loop back to head
            
            System.out.println("(Back to Head)");
        }
    }
}
```

---

## Output

```text
10 -> 20 -> 30 -> (Back to Head)
```

---

## Key Points

- You **must** use a `do-while` loop for traversal, otherwise the loop condition `current != head` will fail immediately on the first iteration.
