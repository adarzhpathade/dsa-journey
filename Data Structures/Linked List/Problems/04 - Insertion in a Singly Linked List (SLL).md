# Insertion in a Singly Linked List (SLL)

#dsa #java #linkedlist #sll #insertion

> Concept: [[Singly Linked List (SLL)]]

## Problem Statement

Implement insertion operations in a Singly Linked List:
- Insert at Beginning
- Insert at End
- Insert at Position

---

## Approach & Code (Sub-operations)

### 1. `insertAtBeginning()`

- Naya node create karo.
- Naye node ke `next` pointer ko current `head` par point karao.
- `head` ko update karke naye node par set kar do.

```java
public void insertAtBeginning(int data) {
    Node newNode = new Node(data);
    newNode.next = head;
    head = newNode;
}
```

#### Visual Example

Before: `10 → 20 → 30 → null`  
After inserting `5` at beginning: `5 → 10 → 20 → 30 → null`

---

### 2. `insertAtEnd()`

- Naya node create karo.
- Agar list empty hai (`head == null`), toh naye node ko hi `head` bana do.
- List ke last node tak traverse karo (`while(temp.next != null)`).
- Last node ke `next` ko naye node se connect kar do.

```java
public void insertAtEnd(int data) {
    Node newNode = new Node(data);

    if (head == null) {
        head = newNode;
        return;
    }

    Node temp = head;

    while (temp.next != null) {
        temp = temp.next;
    }

    temp.next = newNode;
}
```

#### Visual Example

Before: `10 → 20 → 30 → null`  
After inserting `40` at end: `10 → 20 → 30 → 40 → null`

---

### 3. `insertAtPosition()`

- Position valid hai ya nahi check karo.
- Agar position `1` hai, toh `insertAtBeginning()` call karo.
- Specified position se ek pehle wale node (i.e. `position - 1`) tak traverse karo.
- Naye node ke `next` ko `temp.next` par point karao, fir `temp.next = newNode` set karo.

```java
public void insertAtPosition(int data, int position) {

    if (position < 1) {
        System.out.println("Invalid Position");
        return;
    }

    if (position == 1) {
        insertAtBeginning(data);
        return;
    }

    Node newNode = new Node(data);
    Node temp = head;

    for (int i = 1; i < position - 1 && temp != null; i++) {
        temp = temp.next;
    }

    if (temp == null) {
        System.out.println("Position Out of Range");
        return;
    }

    newNode.next = temp.next;
    temp.next = newNode;
}
```

#### Visual Example

Before: `10 → 20 → 40 → 50 → null`  
After inserting `30` at position `3`: `10 → 20 → 30 → 40 → 50 → null`

---

## Time & Space Complexity

| Operation | Time Complexity | Auxiliary Space |
| ---------- | :--: | :---: |
| Insert at Beginning | **$O(1)$** | **$O(1)$** |
| Insert at End | **$O(N)$** | **$O(1)$** |
| Insert at Position | **$O(N)$** | **$O(1)$** |