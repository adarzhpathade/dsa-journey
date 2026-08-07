Insertion in an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Insert an element into a specific index of an **ArrayList**.

---

## Approach

- Use `list.add(element)` to add an element at the end of the ArrayList.
- Use `list.add(index, element)` to insert an element at a specific index.

---

## Code

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        
        // Appending to the end
        list.add(10);
        list.add(20);
        list.add(40);
        
        System.out.println("Before insertion: " + list);

        // Inserting at specific index
        list.add(2, 30); // Insert 30 at index 2

        System.out.println("After insertion: " + list);
    }
}
```

---

## Output

```text
Before insertion: [10, 20, 40]
After insertion: [10, 20, 30, 40]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Append (at end) | O(1) amortized |
| Insert (at index) | O(N) |

---

## Key Points

- `ArrayList` handles resizing and element shifting internally.
- Inserting at index 0 or in the middle is O(N) because elements still need to be shifted under the hood.
