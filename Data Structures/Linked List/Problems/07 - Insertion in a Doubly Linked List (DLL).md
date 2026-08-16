# Insertion in a Doubly Linked List (DLL)

#dsa #java #linkedlist #dll

> **Concept:** [[Doubly Linked List (DLL)]]

## Problem Statement

Insert a new node at the **beginning** of a Doubly Linked List.

---

## Code (Java)

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

        // Naye node ke next ko current head banao aur prev ko null
        newNode.next = head;
        newNode.prev = null;

        // Agar head empty nahi tha, toh purane head ke prev ko naye node se link karo
        if (head != null) {
            head.prev = newNode;
        }

        // Head pointer ko update karke naye node par set kar do
        head = newNode;
    }

    public static void main(String[] args) {
        insertAtBeginning(30);
        insertAtBeginning(20);
        insertAtBeginning(10); // 10 ab naya head ban jayega

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

## Key Points (Khaas Baatein)

- DLL mein head insert karte waqt purane head ke `prev` pointer ko hamesha naye node se connect karna hota hai (jab tak ki initial list completely empty na ho).

