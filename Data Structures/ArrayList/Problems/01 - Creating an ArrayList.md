Creating an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Create a dynamic **ArrayList** in Java, add elements to it, and access them.

---

## Approach

- Instantiate an `ArrayList` object.
- Use the `add(element)` method to insert elements at the end.
- Use the `get(index)` method to access an element.

---

## Code

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        // Initialization
        ArrayList<Integer> list = new ArrayList<>();
        
        // Adding elements
        list.add(10);
        list.add(20);
        list.add(30);

        // Accessing elements
        System.out.println("First element: " + list.get(0));
        System.out.println("Second element: " + list.get(1));
    }
}
```

---

## Output

```text
First element: 10
Second element: 20
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Appending element | O(1) amortized |
| Accessing by index | O(1) |

---

## Key Points

- ArrayList size grows dynamically.
- Requires wrapper classes (e.g., `Integer` instead of `int`).
