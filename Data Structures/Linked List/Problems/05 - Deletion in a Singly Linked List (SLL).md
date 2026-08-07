#dsa #java #linkedlist #sll #deletion

> Concept: [[Singly Linked List (SLL)]]

## Problem Statement

Implement deletion operations in a Singly Linked List:
- Delete from Beginning
- Delete from End
- Delete from Position

---

## Approach

### `deleteFromBeginning()`

- Check if the list is empty.
- Move the head to the next node.
- The previous head node is automatically removed by the Garbage Collector.

### Code

```java
public void deleteFromBeginning() {
    if (head == null) {
        System.out.println("List is Empty");
        return;
    }

    head = head.next;
}
```

### Example

Before

```text
10 → 20 → 30 → 40 → null
```

After

```text
20 → 30 → 40 → null
```

---

### `deleteFromEnd()`

- Check if the list is empty.
- If only one node exists, make the head `null`.
- Traverse to the second last node.
- Set its `next` to `null`.

### Code

```java
public void deleteFromEnd() {
    if (head == null) {
        System.out.println("List is Empty");
        return;
    }

    if (head.next == null) {
        head = null;
        return;
    }

    Node temp = head;

    while (temp.next.next != null) {
        temp = temp.next;
    }

    temp.next = null;
}
```

### Example

Before

```text
10 → 20 → 30 → 40 → null
```

After

```text
10 → 20 → 30 → null
```

---

### `deleteFromPosition()`

- Validate the position.
- If the position is `1`, delete from the beginning.
- Traverse to the node before the desired position.
- Skip the node to be deleted by updating the links.

### Code

```java
public void deleteFromPosition(int position) {

    if (head == null) {
        System.out.println("List is Empty");
        return;
    }

    if (position < 1) {
        System.out.println("Invalid Position");
        return;
    }

    if (position == 1) {
        deleteFromBeginning();
        return;
    }

    Node temp = head;

    for (int i = 1; i < position - 1 && temp != null; i++) {
        temp = temp.next;
    }

    if (temp == null || temp.next == null) {
        System.out.println("Position Out of Range");
        return;
    }

    temp.next = temp.next.next;
}
```

### Example

Before

```text
10 → 20 → 30 → 40 → 50 → null
```

Delete node at position `3`

After

```text
10 → 20 → 40 → 50 → null
```

---

## Time & Space Complexity

| Operation | Time | Space |
| ---------- | :--: | :---: |
| Delete from Beginning | `O(1)` | `O(1)` |
| Delete from End | `O(n)` | `O(1)` |
| Delete from Position | `O(n)` | `O(1)` |