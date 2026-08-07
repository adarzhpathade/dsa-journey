Reversing an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Reverse the elements of an **ArrayList** in-place.

---

## Approach

- **Method 1:** Use `Collections.reverse(list)` for the built-in way.
- **Method 2:** Use two pointers (`start` and `end`), swapping elements using `list.set()` and `list.get()`.

---

## Code

```java
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(10);
        list.add(20);
        list.add(30);
        list.add(40);

        // Built-in approach
        Collections.reverse(list);
        System.out.println("After built-in reverse: " + list);

        // Two-pointer approach
        int start = 0;
        int end = list.size() - 1;

        while (start < end) {
            int temp = list.get(start);
            list.set(start, list.get(end));
            list.set(end, temp);

            start++;
            end--;
        }

        System.out.println("After manual reverse again: " + list);
    }
}
```

---

## Output

```text
After built-in reverse: [40, 30, 20, 10]
After manual reverse again: [10, 20, 30, 40]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Reversing | O(N) |

---

## Key Points

- `Collections.reverse()` is the standard and most readable way in Java.
- Manual reversal requires `set()` method instead of array index assignment `[]`.
