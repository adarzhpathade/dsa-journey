# Printing an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Traverse and print all elements of an **ArrayList**.

---

## Approach (Tarika)

- `list.size()` aur `list.get(i)` ke saath standard `for` loop use karo.
- Clean code ke liye `for-each` loop use kar sakte ho.
- Direct `list` object ko print kar sakte ho kyunki `ArrayList` mein `toString()` overloaded hota hai.

---

## Code (Java)

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        list.add(10);
        list.add(20);
        list.add(30);

        // Method 1: Standard for-loop
        for (int i = 0; i < list.size(); i++) {
            System.out.print(list.get(i) + " ");
        }
        System.out.println();

        // Method 2: For-each loop
        for (int num : list) {
            System.out.print(num + " ");
        }
        System.out.println();

        // Method 3: Direct object print
        System.out.println(list);
    }
}
```

---

## Output

```text
10 20 30 
10 20 30 
[10, 20, 30]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Traversing | $O(N)$ |

---

## Key Points (Khaas Baatein)

- `size()` present elements ki count deta hai, total capacity nahi.
- Debugging ke waqt direct `System.out.println(list)` print karna sabse convenient tarika hota hai.

