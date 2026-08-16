# Creating and Traversing a Circular Linked List (CLL)

#dsa #java #linkedlist #cll

> **Concept:** [[Circular Linked List (CLL)]]

## Problem Statement

Create a Circular Linked List and traverse it until it reaches the head again.

---

## Code (Java)

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
        // Last node ko head se connect karke list ko circular banao
        third.next = head; 

        // Traversal
        if (head != null) {
            Node current = head;
            do {
                System.out.print(current.data + " -> ");
                current = current.next;
            } while (current != head); // Jab tak wapas head tak na pahunch jayein stop mat karo
            
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

## Key Points (Khaas Baatein)

- CLL traversal ke liye **`do-while`** loop use karna mandatory hai, varna standard `while(current != head)` loop condition pehle hi iteration par fail ho jayegi kyunki initial stage par `current = head` hota hai.

