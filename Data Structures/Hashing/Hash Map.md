# Hash Map

#dsa #java #collections #hashing

## Formal Definition

A **HashMap** is a data structure in the Java Collections Framework that stores data in **key-value pairs**, using a hashing mechanism to map keys to their corresponding values with $O(1)$ average time complexity.

- Each **key** must be unique.
- Duplicate **values** are allowed.
- Does **not** maintain insertion order.
- Allows **one `null` key** and **multiple `null` values**.
- Provides **$O(1)$** average time complexity for insertion, deletion, and searching.

---

# Syntax

```java
HashMap<KeyType, ValueType> map = new HashMap<>();
```

### Example

```java
HashMap<Integer, String> map = new HashMap<>();
```

---

# Common Methods (Aam Method Functions)

| Method | Description (Kaam) |
|---------|-------------|
| `put(K key, V value)` | Key-value pair insert ya update karta hai. |
| `get(Object key)` | Specified key se associated value return karta hai. |
| `remove(Object key)` | Specified key-value pair ko map se remove karta hai. |
| `containsKey(Object key)` | Check karta hai kya specified key map mein exist karti hai. |
| `containsValue(Object value)` | Check karta hai kya specified value map mein exist karti hai. |
| `size()` | Total key-value pairs ki count return karta hai. |
| `isEmpty()` | Agar map khali hai toh `true` return karta hai. |
| `clear()` | Saare key-value pairs ko remove/clear kar deta hai. |
| `keySet()` | Saari keys ka Set return karta hai. |
| `values()` | Saari values ki Collection return karta hai. |
| `entrySet()` | Saare key-value pairs (Entry objects) ka Set return karta hai. |
| `getOrDefault(K key, V defaultValue)` | Key ki value return karta hai, aur agar key na mile toh default value return karta hai. |
| `putIfAbsent(K key, V value)` | Pair tabhi insert karta hai jab key pehle se present na ho. |
| `replace(K key, V value)` | Existing key ki value ko nayi value se replace karta hai. |

---

# Code Example (Java)

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {

        HashMap<Integer, String> map = new HashMap<>();

        // Elements add karna
        map.put(1, "Apple");
        map.put(2, "Banana");
        map.put(3, "Mango");

        System.out.println(map.get(2));          // Output: Banana
        System.out.println(map.containsKey(1));  // Output: true
        System.out.println(map.size());          // Output: 3

        // Element remove karna
        map.remove(3);

        System.out.println(map);
    }
}
```

---

# Iterating a HashMap (Loop Chalana)

### Using `keySet()`

```java
for (Integer key : map.keySet()) {
    System.out.println(key + " -> " + map.get(key));
}
```

### Using `entrySet()` (Recommended)

```java
for (Map.Entry<Integer, String> entry : map.entrySet()) {
    System.out.println(entry.getKey() + " -> " + entry.getValue());
}
```

---

# Advantages (Fayde)

- Insertion, deletion, aur searching mein super fast average time ($O(1)$).
- Data ko intuitive **Key → Value** pairs mein store karta hai.
- Ek `null` key aur multiple `null` values allow karta hai.
- Key ke zariye direct data access karna extremely easy hai.

---

# Disadvantages (Nuksan)

- Insertion order maintain nahi rehta (Unordered data structure).
- Non-synchronized hota hai (by default thread-safe nahi hai).
- High hash collisions hone par performance degrade hokar $O(N)$ tak ja sakti hai.

---

# Time Complexity

| Operation | Average Time | Worst Case Time |
|-----------|--------------|------------------|
| Insert (`put`) | **$O(1)$** | **$O(N)$** |
| Search (`get`) | **$O(1)$** | **$O(N)$** |
| Delete (`remove`) | **$O(1)$** | **$O(N)$** |

---

# Quick Revision (Dhyaan Dene Yagya Baatein)

- **Key → Value** mapping store karta hai.
- Keys hamesha **unique** hoti hain.
- Values duplicate ho sakti hain.
- Insertion order preserve nahi hota.
- Max **1 null key** aur multiple null values support karta hai.
- Average time complexity: **$O(1)$**.