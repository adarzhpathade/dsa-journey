# Deletion in an ArrayList

#dsa #java #arraylist

> **Concept:** [[ArrayList]]

## Problem Statement

Delete an element from an **ArrayList** by index or by value.

---

## Approach (Tarika)

- Specific index se element remove karne ke liye `list.remove(index)` ka use karo.
- Specific value ki pehli occurrence ko delete karne ke liye `list.remove(Object)` ka use karo.

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
        list.add(40);
        list.add(50);

        System.out.println("Initial List: " + list);

        // Index ke dwara remove karna
        list.remove(2); // Index 2 wale element ('30') ko remove karega
        System.out.println("After removing index 2: " + list);

        // Value ke dwara remove karna (Integers ke liye Object wrapping zaroori hai)
        list.remove(Integer.valueOf(50));
        System.out.println("After removing value 50: " + list);
    }
}
```

---

## Output

```text
Initial List: [10, 20, 30, 40, 50]
After removing index 2: [10, 20, 40, 50]
After removing value 50: [10, 20, 40]
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Remove (last element)| $O(1)$ |
| Remove (middle/start)| $O(N)$ |

---

## Key Points (Khaas Baatein)

- `ArrayList<Integer>` ke saath kaam karte waqt `remove(2)` default index 2 maanta hai. Integer value 2 ko remove karne ke liye `remove(Integer.valueOf(2))` pass karna hota hai.
- Insertion ki tarah, deletion mein bhi internally items shifted hote hain.

