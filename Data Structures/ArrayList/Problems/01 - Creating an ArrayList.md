# Creating an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Create a dynamic **ArrayList** in Java, add elements to it, and access them.

---

## Approach (Tarika)

- `ArrayList` class ka object instantiate karo.
- End mein elements add karne ke liye `add(element)` method ka use karo.
- Index se element access karne ke liye `get(index)` method ka use karo.

---

## Code (Java)

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        // Initialization
        ArrayList<Integer> list = new ArrayList<>();
        
        // Elements add karna
        list.add(10);
        list.add(20);
        list.add(30);

        // Elements access karna
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
| Appending element | $O(1)$ amortized |
| Accessing by index | $O(1)$ |

---

## Key Points (Khaas Baatein)

- ArrayList ka size dynamically automatically grow hota rehta hai.
- Primitive types ke liye Wrapper classes (`int` ke bajaye `Integer`) use karni padti hain.

