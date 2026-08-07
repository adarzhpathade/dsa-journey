Deletion in an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Delete an element from an **ArrayList** by index or by value.

---

## Approach

- Use `list.remove(index)` to delete the element at a specific position.
- Use `list.remove(Object)` to delete the first occurrence of a specific value.

---

## Code

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(10);
        list.add(20);
        list.add(30);
        list.add(40);
        list.add(50);

        System.out.println("Initial List: " + list);

        // Remove by index
        list.remove(2); // Removes element at index 2 (which is 30)
        System.out.println("After removing index 2: " + list);

        // Remove by value (requires wrapping in an Object for integers)
        list.remove(Integer.valueOf(50));
        System.out.println("After removing value 50: " + list);
    }
}
```

---

## Output

```text
Initial List: [10, 20, 30, 40, 50]
After removing index 2: [10, 20, 40, 50]
After removing value 50: [10, 20, 40]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Remove (last element)| O(1) |
| Remove (middle/start)| O(N) |

---

## Key Points

- When dealing with an `ArrayList<Integer>`, using `remove(2)` defaults to index. To remove the integer value 2, use `remove(Integer.valueOf(2))`.
- Like insertion, deletion involves shifting elements internally.
