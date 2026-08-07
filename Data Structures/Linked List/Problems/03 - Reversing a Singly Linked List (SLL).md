Reversing a Singly Linked List (SLL)

#dsa #java #linkedlist #sll

> **Concept:** [[Singly Linked List (SLL)]]

## Problem Statement

Reverse a **Singly Linked List** so that the last node becomes the first node and all the links are reversed.

---

## Approach

- Initialize three pointers:
  - `prev` → `null`
  - `current` → `head`
  - `next` → `null`
- Traverse the list.
- Store the next node in `next`.
- Reverse the current node's link.
- Move `prev` and `current` one step forward.
- After traversal, assign `head = prev`.

---

## Code

```java
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class Main {

    static Node reverse(Node head) {

        Node prev = null;
        Node current = head;
        Node next = null;

        while (current != null) {

            next = current.next;
            current.next = prev;

            prev = current;
            current = next;
        }

        return prev;
    }

    static void printList(Node head) {

        while (head != null) {
            System.out.print(head.data + " -> ");
            head = head.next;
        }

        System.out.println("null");
    }

    public static void main(String[] args) {

        Node head = new Node(10);
        head.next = new Node(20);
        head.next.next = new Node(30);
        head.next.next.next = new Node(40);

        System.out.println("Original List:");
        printList(head);

        head = reverse(head);

        System.out.println("Reversed List:");
        printList(head);
    }
}
```

---

## Output

```text
Original List:
10 -> 20 -> 30 -> 40 -> null

Reversed List:
40 -> 30 -> 20 -> 10 -> null
```

---

## Dry Run

### Before Reversing

```text
Head
 │
 ▼
10 ───► 20 ───► 30 ───► 40 ───► null
```

### Iteration 1

```text
prev     current      next
null      10   ───►    20

Reverse Link

10 ───► null

prev = 10
current = 20
```

### Iteration 2

```text
10 ◄── 20      30 ───► 40

prev = 20
current = 30
```

### Iteration 3

```text
10 ◄── 20 ◄── 30      40

prev = 30
current = 40
```

### Iteration 4

```text
10 ◄── 20 ◄── 30 ◄── 40

prev = 40
current = null
```

### Final List

```text
Head
 │
 ▼
40 ───► 30 ───► 20 ───► 10 ───► null
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Reverse | **O(n)** |

---

## Space Complexity

| Complexity |
|------------|
| **O(1)** |

---

## Key Points

- Uses **three pointers**: `prev`, `current`, and `next`.
- Reverse the `next` pointer of every node.
- The last node becomes the new **head**.
- The list is reversed **in-place**, requiring no extra memory.
- This is the most efficient iterative approach.