# Reversing an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Reverse the elements of an **ArrayList** in-place.

---

## Approach (Tarika)

- **Method 1 (Built-in):** Built-in method `Collections.reverse(list)` ka use karo.
- **Method 2 (Two-Pointer):** Two pointers (`start` aur `end`) set karo, aur `list.set()` & `list.get()` ka use karke values swap karo.

---

## Code (Java)

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

        // Built-in method se reverse
        Collections.reverse(list);
        System.out.println("After built-in reverse: " + list);

        // Two-pointer method se manual reverse
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
| Reversing | $O(N)$ |

---

## Key Points (Khaas Baatein)

- `Collections.reverse()` Java mein list reverse karne ka standard aur most readable tarika hai.
- Manual reversal mein direct `arr[i]` bracket assign karne ke bajaye `set(index, value)` method ka use hota hai.

