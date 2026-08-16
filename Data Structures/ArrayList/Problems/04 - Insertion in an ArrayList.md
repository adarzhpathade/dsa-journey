# Insertion in an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Insert an element into a specific index of an **ArrayList**.

---

## Approach (Tarika)

- ArrayList ke end mein element add karne ke liye `list.add(element)` method ka use karo.
- Specific index par element insert karne ke liye `list.add(index, element)` method ka use karo.

---

## Code (Java)

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        
        // End mein elements append karna
        list.add(10);
        list.add(20);
        list.add(40);
        
        System.out.println("Before insertion: " + list);

        // Specific index par element insert karna
        list.add(2, 30); // Index 2 par '30' insert karo

        System.out.println("After insertion: " + list);
    }
}
```

---

## Output

```text
Before insertion: [10, 20, 40]
After insertion: [10, 20, 30, 40]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Append (at end) | $O(1)$ amortized |
| Insert (at index) | $O(N)$ |

---

## Key Points (Khaas Baatein)

- `ArrayList` memory resizing aur elements ka right shift internal code se manage kar leta hai.
- Index 0 ya middle mein insert karna $O(N)$ hota hai kyunki internal elements ko Shift hona padta hai.

