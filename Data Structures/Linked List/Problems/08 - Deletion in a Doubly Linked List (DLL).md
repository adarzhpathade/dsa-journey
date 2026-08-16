# Deletion in a Doubly Linked List (DLL)

#dsa #java #linkedlist #dll

> **Concept:** [[Doubly Linked List (DLL)]]

## Problem Statement

Delete a given node from a Doubly Linked List.

---

## Code (Java)

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

        // Agar delete hone wala node head node hi hai
        if (head == del) {
            head = del.next;
        }

        // Agle node ka prev pointer update karo tabhi agar del last node NA ho
        if (del.next != null) {
            del.next.prev = del.prev;
        }

        // Pichle node ka next pointer update karo tabhi agar del pehla node NA ho
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

        // Middle node (20) ko delete karo
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

## Key Points (Khaas Baatein)

- DLL mein direct node pointer pata hone par deletion SLL se zyaada easy hota hai kyunki humare paas `prev` pointer hota hai aur piche wale node tak poori list traverse karne ki zaroorat nahi padti.

