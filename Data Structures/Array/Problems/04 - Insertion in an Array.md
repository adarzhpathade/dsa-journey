# Insertion in an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Insert an element into a specific index of an **Array**.

---

## Approach (Tarika)

Arrays ka size fixed hota hai, isliye element insert karne ke liye array poori tarah bhara hua nahi hona chahiye.
- Target index se lekar last element tak saare items ko ek position right side shift (`arr[i+1] = arr[i]`) karo.
- Jab target index khali ho jaye, toh wahan naya element daal do.
- Array ka logical size (`size++`) update kar do.

---

## Code (Java)

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = new int[6]; // Total capacity = 6
        arr[0] = 10;
        arr[1] = 20;
        arr[2] = 40;
        arr[3] = 50;
        int size = 4; // Abhi present elements ki count

        int elementToInsert = 30;
        int targetIndex = 2;

        // Target index se aage ke elements ko right shift karo
        for (int i = size - 1; i >= targetIndex; i--) {
            arr[i + 1] = arr[i];
        }

        // Element insert karo
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
| Insertion (at end) | $O(1)$ |
| Insertion (at beginning/middle) | $O(N)$ |

---

## Key Points (Khaas Baatein)

- Arrays memory mein contiguous hote hain, isliye middle insertion ke liye elements ko right shift karna hi padta hai.
- Agar array pehle se fully full hai, toh bina naya bada array banaye insertion impossible hai.
