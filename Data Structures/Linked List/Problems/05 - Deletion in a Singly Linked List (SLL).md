# Deletion in a Singly Linked List (SLL)

#dsa #java #linkedlist #sll #deletion

> Concept: [[Singly Linked List (SLL)]]

## Problem Statement

Implement deletion operations in a Singly Linked List:
- Delete from Beginning
- Delete from End
- Delete from Position

---

## Approach & Code (Sub-operations)

### 1. `deleteFromBeginning()`

- Check karo kya list empty (`head == null`) hai.
- `head` pointer ko uske next node par shift kar do (`head = head.next`).
- Purana pehla node Java ka Garbage Collector automatically memory se remove kar dega.

```java
public void deleteFromBeginning() {
    if (head == null) {
        System.out.println("List is Empty");
        return;
    }

    head = head.next;
}
```

#### Visual Example

Before: `10 → 20 → 30 → 40 → null`  
After: `20 → 30 → 40 → null`

---

### 2. `deleteFromEnd()`

- Check karo kya list empty hai.
- Agar list mein sirf ek hi node hai, toh `head = null` set karke return kar jao.
- List ke second last node (`temp.next.next != null`) tak traverse karo.
- Second last node ke `next` pointer ko `null` par set kar do (`temp.next = null`).

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

#### Visual Example

Before: `10 → 20 → 30 → 40 → null`  
After: `10 → 20 → 30 → null`

---

### 3. `deleteFromPosition()`

- Check karo position valid hai ya nahi.
- Agar position `1` hai, toh `deleteFromBeginning()` call karo.
- Targeted position se ek pehle wale node (`position - 1`) tak traverse karo.
- Links update karke middle node ko skip kar do (`temp.next = temp.next.next`).

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

#### Visual Example

Before: `10 → 20 → 30 → 40 → 50 → null`  
Deleting node at position `3`  
After: `10 → 20 → 40 → 50 → null`

---

## Time & Space Complexity

| Operation | Time Complexity | Auxiliary Space |
| ---------- | :--: | :---: |
| Delete from Beginning | **$O(1)$** | **$O(1)$** |
| Delete from End | **$O(N)$** | **$O(1)$** |
| Delete from Position | **$O(N)$** | **$O(1)$** |