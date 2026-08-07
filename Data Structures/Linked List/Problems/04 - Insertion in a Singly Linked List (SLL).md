Insertion in a Singly Linked List (SLL)

#dsa #java #linkedlist #sll #insertion

> Concept: [[Singly Linked List (SLL)]]

## Problem Statement

Implement insertion operations in a Singly Linked List:
- Insert at Beginning
- Insert at End
- Insert at Position

---

## Approach

### `insertAtBeginning()`

- Create a new node.
- Point the new node to the current head.
- Update the head to the new node.

### Code

```java
public void insertAtBeginning(int data) {
    Node newNode = new Node(data);
    newNode.next = head;
    head = newNode;
}
```

### Example

Before

```text
10 → 20 → 30 → null
```

After

```text
5 → 10 → 20 → 30 → null
```

---

### `insertAtEnd()`

- Create a new node.
- If the list is empty, make the new node the head.
- Traverse until the last node.
- Connect the last node to the new node.

### Code

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

### Example

Before

```text
10 → 20 → 30 → null
```

After

```text
10 → 20 → 30 → 40 → null
```

---

### `insertAtPosition()`

- Validate the position.
- If the position is `1`, insert at the beginning.
- Traverse to the node before the desired position.
- Adjust the links.
- Insert the new node.

### Code

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

### Example

Before

```text
10 → 20 → 40 → 50 → null
```

After inserting `30` at position `3`

```text
10 → 20 → 30 → 40 → 50 → null
```

---

## Time & Space Complexity

| Operation | Time | Space |
| ---------- | :--: | :---: |
| Insert at Beginning | `O(1)` | `O(1)` |
| Insert at End | `O(n)` | `O(1)` |
| Insert at Position | `O(n)` | `O(1)` |