Insertion in an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Insert an element into a specific index of an **Array**.

---

## Approach

Since Arrays have a fixed size, to insert an element, the array must not be full.
- Shift all elements from the target index to the end one position to the right.
- Insert the new element at the target index.
- Increment the logical size of the array.

---

## Code

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = new int[6]; // Capacity of 6
        arr[0] = 10;
        arr[1] = 20;
        arr[2] = 40;
        arr[3] = 50;
        int size = 4; // Current number of elements

        int elementToInsert = 30;
        int targetIndex = 2;

        // Shift elements to the right
        for (int i = size - 1; i >= targetIndex; i--) {
            arr[i + 1] = arr[i];
        }

        // Insert
        arr[targetIndex] = elementToInsert;
        size++;

        System.out.println(Arrays.toString(arr));
    }
}
```

---

## Output

```text
[10, 20, 30, 40, 50, 0]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Insertion (at end) | O(1) |
| Insertion (at beginning/middle) | O(N) |

---

## Key Points

- Because arrays are contiguous in memory, shifting is required.
- If the array is full, you cannot insert without creating a new, larger array first.
