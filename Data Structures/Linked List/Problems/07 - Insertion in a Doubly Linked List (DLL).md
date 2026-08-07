Insertion in a Doubly Linked List (DLL)

#dsa #java #linkedlist #dll

> **Concept:** [[Doubly Linked List (DLL)]]

## Problem Statement

Insert a new node at the **beginning** of a Doubly Linked List.

---

## Code

```java
class Node {
    int data;
    Node prev, next;
    Node(int data) { this.data = data; this.prev = this.next = null; }
}

public class Main {
    static Node head;

    public static void insertAtBeginning(int newData) {
        Node newNode = new Node(newData);

        // Make next of new node as head and previous as null
        newNode.next = head;
        newNode.prev = null;

        // Change prev of head node to new node
        if (head != null) {
            head.prev = newNode;
        }

        // Move the head to point to the new node
        head = newNode;
    }

    public static void main(String[] args) {
        insertAtBeginning(30);
        insertAtBeginning(20);
        insertAtBeginning(10); // 10 will become the new head

        Node current = head;
        while (current != null) {
            System.out.print(current.data + " <-> ");
            current = current.next;
        }
        System.out.println("null");
    }
}
```

---

## Output

```text
10 <-> 20 <-> 30 <-> null
```

---

## Key Points

- Always update the `prev` pointer of the old head to point to the new node, **unless** the list was empty.
