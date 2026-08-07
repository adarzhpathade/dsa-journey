#dsa #java #collections #hashing

## Definition

`HashMap` is a class in the Java Collections Framework that stores data in **key-value pairs**.

- Each **key** must be unique.
- Duplicate **values** are allowed.
- Does **not** maintain insertion order.
- Allows **one `null` key** and **multiple `null` values**.
- Provides **O(1)** average time complexity for insertion, deletion, and searching.

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

# Common Methods

| Method | Description |
|---------|-------------|
| `put(K key, V value)` | Inserts or updates a key-value pair. |
| `get(Object key)` | Returns the value associated with the specified key. |
| `remove(Object key)` | Removes the key-value pair from the map. |
| `containsKey(Object key)` | Checks if the specified key exists. |
| `containsValue(Object value)` | Checks if the specified value exists. |
| `size()` | Returns the number of key-value pairs. |
| `isEmpty()` | Returns `true` if the map is empty. |
| `clear()` | Removes all key-value pairs. |
| `keySet()` | Returns a set of all keys. |
| `values()` | Returns a collection of all values. |
| `entrySet()` | Returns a set of all key-value pairs. |
| `getOrDefault(K key, V defaultValue)` | Returns the value for the key, or the default value if the key is not found. |
| `putIfAbsent(K key, V value)` | Inserts the key-value pair only if the key is not already present. |
| `replace(K key, V value)` | Replaces the value of an existing key. |

---

# Example

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {

        HashMap<Integer, String> map = new HashMap<>();

        map.put(1, "Apple");
        map.put(2, "Banana");
        map.put(3, "Mango");

        System.out.println(map.get(2));          // Banana
        System.out.println(map.containsKey(1));  // true
        System.out.println(map.size());          // 3

        map.remove(3);

        System.out.println(map);
    }
}
```

---

# Iterating a HashMap

### Using `keySet()`

```java
for (Integer key : map.keySet()) {
    System.out.println(key + " -> " + map.get(key));
}
```

### Using `entrySet()`

```java
for (Map.Entry<Integer, String> entry : map.entrySet()) {
    System.out.println(entry.getKey() + " -> " + entry.getValue());
}
```

---

# Advantages

- Fast insertion, deletion, and searching.
- Stores data as key-value pairs.
- Allows one `null` key and multiple `null` values.
- Easy to retrieve data using keys.

---

# Disadvantages

- Does not maintain insertion order.
- Not synchronized (not thread-safe).
- Performance may decrease if many hash collisions occur.

---

# Time Complexity

| Operation | Average Time |
|-----------|--------------|
| Insert (`put`) | **O(1)** |
| Search (`get`) | **O(1)** |
| Delete (`remove`) | **O(1)** |

---

# Quick Revision

- Stores **Key → Value** pairs.
- Keys are **unique**.
- Duplicate values are **allowed**.
- No insertion order is maintained.
- Allows **1 null key** and **multiple null values**.
- Average time complexity: **O(1)**.