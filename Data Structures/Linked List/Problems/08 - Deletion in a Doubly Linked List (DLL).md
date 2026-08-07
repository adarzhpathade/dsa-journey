Deletion in a Doubly Linked List (DLL)

#dsa #java #linkedlist #dll

> **Concept:** [[Doubly Linked List (DLL)]]

## Problem Statement

Delete a given node from a Doubly Linked List.

---

## Code

```java
class Node {
    int data;
    Node prev, next;
    Node(int data) { this.data = data; }
}

public class Main {
    static Node head;

    public static void deleteNode(Node del) {
        if (head == null || del == null) return;

        // If node to be deleted is head node
        if (head == del) {
            head = del.next;
        }

        // Change next only if node to be deleted is NOT the last node
        if (del.next != null) {
            del.next.prev = del.prev;
        }

        // Change prev only if node to be deleted is NOT the first node
        if (del.prev != null) {
            del.prev.next = del.next;
        }
    }

    public static void main(String[] args) {
        head = new Node(10);
        Node second = new Node(20);
        Node third = new Node(30);

        head.next = second; second.prev = head;
        second.next = third; third.prev = second;

        // Delete the middle node (20)
        deleteNode(second);

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
10 <-> 30 <-> null
```

---

## Key Points

- Deletion in a DLL is easier than an SLL if you are given the node itself, because you have the `prev` pointer and don't need to traverse to find the previous node.
