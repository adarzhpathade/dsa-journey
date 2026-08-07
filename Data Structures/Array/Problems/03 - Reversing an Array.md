Reversing an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Reverse the elements of an **Array** in-place.

---

## Approach

- Use two pointers: `start` at index `0` and `end` at index `n - 1`.
- Swap the elements at the `start` and `end` indices.
- Increment `start` and decrement `end`.
- Repeat until `start` >= `end`.

---

## Code

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        
        int start = 0;
        int end = arr.length - 1;

        while (start < end) {
            // Swap
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;

            start++;
            end--;
        }

        System.out.println(Arrays.toString(arr));
    }
}
```

---

## Output

```text
[50, 40, 30, 20, 10]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Reversing | O(N) |
| Space Complexity | O(1) |

---

## Key Points

- In-place reversal saves memory space.
- Two-pointer approach is optimal for this problem.
