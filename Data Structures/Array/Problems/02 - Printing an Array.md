Printing an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Traverse and print all elements of an **Array**.

---

## Approach

- Use a `for` loop from index `0` to `array.length - 1`.
- Alternatively, use a `for-each` loop to iterate through the elements directly.
- `Arrays.toString()` can also be used for quick printing.

---

## Code

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40};

        // Method 1: standard for-loop
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();

        // Method 2: for-each loop
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();

        // Method 3: Arrays.toString()
        System.out.println(Arrays.toString(arr));
    }
}
```

---

## Output

```text
10 20 30 40 
10 20 30 40 
[10, 20, 30, 40]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Traversing/Printing | O(N) |

---

## Key Points

- `.length` property gives the size of the array.
- For-each loop is cleaner when the index is not needed.
