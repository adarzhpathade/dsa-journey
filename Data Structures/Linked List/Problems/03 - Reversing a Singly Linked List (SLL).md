# Reversing a Singly Linked List (SLL)

#dsa #java #linkedlist #sll

> **Concept:** [[Singly Linked List (SLL)]]

## Problem Statement

Reverse a **Singly Linked List** so that the last node becomes the first node and all the links are reversed.

---

## Approach (Iterative Three-Pointer Technique)

- Teen pointers initialize karo:
  - `prev` → `null`
  - `current` → `head`
  - `next` → `null`
- Tab tak list traverse karo jab tak `current != null` rahe.
- Agle node ko `next` pointer mein save kar lo (`next = current.next`).
- Current node ke link ko piche turn kar do (`current.next = prev`).
- `prev` aur `current` pointers ko ek-ek step aage badhao.
- Traversal complete hone ke baad, `head` ko `prev` par point kara do (`head = prev`).

---

## Code (Java)

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

            next = current.next;    // Agle node ko store karo
            current.next = prev;    // Link reverse karo

            prev = current;         // Pointers ko aage move karo
            current = next;
        }

        return prev; // Naya head return karo
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

### Final Reversed List

```text
Head
 │
 ▼
40 ───► 30 ───► 20 ───► 10 ───► null
```

---

## Time & Space Complexity

| Operation | Time Complexity | Auxiliary Space |
|-----------|-----------------|------------------|
| Reverse | **$O(N)$** | **$O(1)$** |

---

## Key Points (Khaas Baatein)

- **Teen pointers** ka use hota hai: `prev`, `current`, aur `next`.
- Har node ke `next` pointer direction ko reverse kar diya jata hai.
- Original list ka last node final reversed list ka naya **head** ban jata hai.
- Reversal **in-place** hoti hai, isliye zero extra memory allocate hoti hai ($O(1)$ space).
- Single pass mein solve hone wala sabse efficient iterative algorithm hai.