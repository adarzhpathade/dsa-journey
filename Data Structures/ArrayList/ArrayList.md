#dsa #java #arraylist 


An **ArrayList** is a resizable-array implementation of the `List` interface in Java (and similar dynamic array structures in other languages). Unlike standard arrays, an ArrayList can dynamically grow and shrink in size as elements are added or removed.

Elements are stored contiguously in memory, allowing for fast random access.

---

## Initialization and Usage

```java
import java.util.ArrayList;

class Main {
    public static void main(String[] args) {
        // Initialization
        ArrayList<Integer> list = new ArrayList<>();
        
        // Adding elements
        list.add(10);
        list.add(20);
        list.add(30);
    }
}
```

---

## Representation

```text
Index:   0    1    2    3
       -------------------
Data:  | 10 | 20 | 30 | 40 |
       -------------------
```

---

## Characteristics

- Dynamic size (automatically resizes when full, usually by 50% or 100%).
- Elements are stored in contiguous memory locations.
- Allows random access using indices.
- Insertion and deletion are slower compared to Linked Lists (if not at the end) because elements need to be shifted.
- Can contain duplicate elements and `null` values.

---

## Advantages

- Dynamic memory allocation (no need to specify initial size).
- Fast random access (O(1) time complexity to get an element by index).
- Cache-friendly due to contiguous memory allocation.
- Provides many built-in methods for data manipulation (sorting, searching, etc.).

---

## Disadvantages

- Slower insertion and deletion operations in the middle or beginning (requires shifting elements).
- Can waste memory if the allocated capacity is much larger than the number of elements actually stored.
- Slightly slower than primitive arrays due to object wrapping and bounds checking.

---

## Applications

- Storing elements where the number of elements is not known in advance.
- When frequent random access is required.
- Building blocks for other data structures like Heaps, Stacks, or Queues.
- Implementing dynamic lists of objects (e.g., list of users, shopping cart items).
