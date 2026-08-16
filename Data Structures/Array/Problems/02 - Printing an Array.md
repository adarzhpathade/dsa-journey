# Printing an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Traverse and print all elements of an **Array**.

---

## Approach (Tarika)

- Standard `for` loop ka use karo index `0` se `arr.length - 1` tak traversal karne ke liye.
- Direct values iterate karne ke liye `for-each` loop ka use kar sakte ho.
- Quick debugging aur printing ke liye `Arrays.toString()` utility method bhi use kar sakte ho.

---

## Code (Java)

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40};

        // Method 1: Standard for-loop
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();

        // Method 2: For-each loop
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();

        // Method 3: Arrays.toString() utility
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
| Traversing/Printing | $O(N)$ |

---

## Key Points (Khaas Baatein)

- `.length` property se array ka exact size milta hai.
- Jab index position ki zarurat na ho, toh `for-each` loop cleaner option hota hai.

