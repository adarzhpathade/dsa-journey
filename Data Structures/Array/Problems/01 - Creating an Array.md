Creating an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Create a fixed-size **Array** in Java, assign values to its indices, and access them.

---

## Approach

- Declare an array of a specific data type and size.
- Assign values to the array using indices.
- Alternatively, use array literal syntax for inline initialization.

---

## Code

```java
public class Main {
    public static void main(String[] args) {
        // Method 1: Declaration with size
        int[] arr1 = new int[3];
        arr1[0] = 10;
        arr1[1] = 20;
        arr1[2] = 30;

        // Method 2: Array literal
        int[] arr2 = {40, 50, 60};

        System.out.println("arr1 first element: " + arr1[0]);
        System.out.println("arr2 first element: " + arr2[0]);
    }
}
```

---

## Output

```text
arr1 first element: 10
arr2 first element: 40
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Creating | O(1) or O(N) |
| Accessing by index | O(1) |

---

## Key Points

- Arrays have a fixed size defined at creation.
- Array indices start at `0`.
