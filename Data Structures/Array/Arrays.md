#dsa #java #array 


An **Array** is a linear data structure that collects elements of the same data type and stores them in contiguous and adjacent memory locations. Arrays are of fixed size, meaning once the size is declared, it cannot be changed dynamically.

They provide a way to store multiple values in a single variable, rather than declaring separate variables for each value.

---

## Initialization and Usage

```java
class Main {
    public static void main(String[] args) {
        // Declaration and Initialization
        int[] arr = new int[5]; // Fixed size of 5
        
        // Assigning values
        arr[0] = 10;
        arr[1] = 20;
        arr[2] = 30;
        
        // Alternatively, array literal
        int[] arr2 = {10, 20, 30, 40, 50};
        
        // Accessing an element
        System.out.println(arr[1]); // Output: 20
    }
}
```

---

## Representation

```text
Index:   0    1    2    3    4
       ------------------------
Data:  | 10 | 20 | 30 | 40 | 50 |
       ------------------------
Memory: 100  104  108  112  116   (Assuming 4 bytes per int)
```

---

## Characteristics

- Fixed size: The capacity must be defined at the time of creation and cannot be modified.
- Contiguous memory allocation: Elements are stored in adjacent memory locations.
- Homogeneous elements: All elements must be of the same data type.
- Zero-indexed: The first element is at index 0, and the last is at index `n - 1`.

---

## Advantages

- **Random Access**: Elements can be accessed directly in O(1) time complexity using their index.
- **Memory Efficiency**: Minimal memory overhead since there are no pointers to next/previous elements (unlike Linked Lists).
- **Cache Friendliness**: Because memory is contiguous, arrays have better spatial locality in CPU cache, leading to faster access times.
- Easy to iterate through and manipulate using loops.

---

## Disadvantages

- **Fixed Size**: Cannot grow or shrink at runtime. If the array is full, a new larger array must be created and elements copied over.
- **Insertion/Deletion**: Slow (O(N) time complexity) when inserting or deleting elements in the middle or beginning, as it requires shifting subsequent elements.
- **Memory Wastage**: If an array is declared with a large size but only a few elements are stored, the remaining memory is wasted.

---

## Applications

- Storing a fixed number of elements (e.g., days of the week, months in a year).
- Implementing other data structures like Stacks, Queues, Heaps, and Hash Tables.
- Used as lookup tables or matrices (2D arrays).
- Sorting and searching algorithms often operate on arrays.
