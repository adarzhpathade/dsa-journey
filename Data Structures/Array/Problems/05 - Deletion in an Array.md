# Deletion in an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Delete an element from a specific index in an **Array**.

---

## Approach (Tarika)

- Delete ki jaane wali position (target index) find karo.
- Target index ke right side wale sabhi elements ko ek position left side shift (`arr[i] = arr[i + 1]`) karo gap ko fill karne ke liye.
- Array ke logical size count ko decrement (`size--`) kar do.

---

## Code (Java)

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        int size = 5;
        
        int targetIndex = 2; // Index 2 par rakhe element '30' ko delete karna hai

        // Elements ko left shift karo gap fill karne ke liye
        for (int i = targetIndex; i < size - 1; i++) {
            arr[i] = arr[i + 1];
        }
        
        // Optional: Last element clear kar sakte ho
        arr[size - 1] = 0;
        size--;

        System.out.print("Array after deletion: ");
        for (int i = 0; i < size; i++) {
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
| Deletion (at end) | $O(1)$ |
| Deletion (at beginning/middle) | $O(N)$ |

---

## Key Points (Khaas Baatein)

- Array mein delete karne ke baad bane gap ko bharne ke liye elements ko left shift karna zaroori hota hai.
- Array ka physical capacity (`arr.length`) wahi rehta hai, bas logical `size` kam hota hai.

