# Creating an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Create a fixed-size **Array** in Java, assign values to its indices, and access them.

---

## Approach (Tarika)

- Ek specific data type aur fixed size ka array declare karo.
- Indices (jaise `arr[0]`, `arr[1]`) ka use karke values assign karo.
- Inline initialization ke liye Array literal syntax (`int[] arr = {10, 20}`) bhi use kar sakte ho.

---

## Code (Java)

```java
public class Main {
    public static void main(String[] args) {
        // Method 1: Size ke saath declaration
        int[] arr1 = new int[3];
        arr1[0] = 10;
        arr1[1] = 20;
        arr1[2] = 30;

        // Method 2: Direct Array literal syntax
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
| Creating | $O(1)$ ya $O(N)$ (JVM memory allocation) |
| Accessing by index | $O(1)$ |

---

## Key Points (Khaas Baatein)

- Arrays ka size creation ke time fix hota hai aur baad mein change nahi kiya ja sakta.
- Array indexing hamesha `0` se shuru hoti hai.

