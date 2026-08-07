Deletion in an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Delete an element from a specific index in an **Array**.

---

## Approach

- Find the index of the element to delete.
- Shift all elements to the right of this index one position to the left.
- Decrement the logical size of the array.

---

## Code

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        int size = 5;
        
        int targetIndex = 2; // Delete element '30'

        // Shift elements to the left
        for (int i = targetIndex; i < size - 1; i++) {
            arr[i] = arr[i + 1];
        }
        
        // Optional: clear the last element (for reference types, to avoid memory leaks)
        arr[size - 1] = 0;
        size--;

        System.out.print("Array after deletion: ");
        for(int i = 0; i < size; i++){
            System.out.print(arr[i] + " ");
        }
    }
}
```

---

## Output

```text
Array after deletion: 10 20 40 50 
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Deletion (at end) | O(1) |
| Deletion (at beginning/middle) | O(N) |

---

## Key Points

- Deletion in an array requires shifting elements to fill the gap.
- The physical size (`arr.length`) remains unchanged, but the logical `size` is reduced.
