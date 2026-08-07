Printing an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Traverse and print all elements of an **ArrayList**.

---

## Approach

- Use a `for` loop with `list.size()` and `list.get(i)`.
- Use a `for-each` loop.
- Directly print the list object (it overrides `toString()`).

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

        // Method 1: standard for-loop
        for (int i = 0; i < list.size(); i++) {
            System.out.print(list.get(i) + " ");
        }
        System.out.println();

        // Method 2: for-each loop
        for (int num : list) {
            System.out.print(num + " ");
        }
        System.out.println();

        // Method 3: Direct print
        System.out.println(list);
    }
}
```

---

## Output

```text
10 20 30 
10 20 30 
[10, 20, 30]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Traversing | O(N) |

---

## Key Points

- `size()` gives the number of elements, not the capacity.
- Direct printing `System.out.println(list)` is very convenient for debugging.
