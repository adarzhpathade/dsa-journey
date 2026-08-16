# ArrayList

#dsa #java #arraylist 

## Formal Definition

An **ArrayList** is a resizable-array implementation of the `List` interface in Java (and similar dynamic array structures in other languages). Unlike standard arrays, an ArrayList can dynamically grow and shrink in size as elements are added or removed.

Elements are stored contiguously in memory, allowing for fast random access.

---

## Initialization and Usage (Java)

```java
import java.util.ArrayList;

class Main {
    public static void main(String[] args) {
        // Initialization
        ArrayList<Integer> list = new ArrayList<>();
        
        // Elements add karna
        list.add(10);
        list.add(20);
        list.add(30);
    }
}
```

---

## Memory Representation

```text
Index:   0    1    2    3
       -------------------
Data:  | 10 | 20 | 30 | 40 |
       -------------------
```

---

## Key Characteristics

- **Dynamic size**: Full hone par automatically apni capacity resize kar leta hai (usually 50% ya 100% badha leta hai).
- Memory mein elements contiguously store hote hain.
- Index ke zariye fast random access allow karta hai.
- Insertion aur deletion operation middle ya start mein slow ($O(N)$) hote hain kyunki elements ko shift karna padta hai.
- Duplicate elements aur `null` values allow karta hai.

---

## Advantages (Fayde)

- **Dynamic Memory Allocation**: Pehle se fixed size define karne ki zaroorat nahi hoti.
- **Fast Random Access**: Index se element retrieve karne ka time complexity $O(1)$ hai.
- **Cache-Friendly**: Memory contiguous hone ki wajah se cache locality acchi hoti hai.
- Built-in methods provide karta hai data manipulation ke liye (sorting, searching, searching by index, etc.).

---

## Disadvantages (Nuksan)

- Middle ya beginning mein insertion aur deletion slow hota hai (shifting required).
- Agar allocated capacity ke mukable kam elements stored hain, toh extra allocated memory waste hoti hai.
- Primitive arrays ke comparison mein object wrapping (Boxing/Unboxing) aur bounds checking ki wajah se thoda slow padta hai.

---

## Applications (Kahan Use Hota Hai?)

- Jab elements ki exact count pehle se pata na ho.
- Jab frequent random access (indexing) ki zaroorat ho.
- Heaps, Stacks, ya Queues jaise data structures banane ke liye building block ke roop mein.
- Objects ki dynamic list maintain karne ke liye (jaise shopping cart items, user list).

