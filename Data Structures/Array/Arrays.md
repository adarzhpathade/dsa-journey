# Arrays

#dsa #java #array 

## Formal Definition

An **Array** is a linear data structure that collects elements of the same data type and stores them in contiguous and adjacent memory locations. Arrays are of fixed size, meaning once the size is declared, it cannot be changed dynamically.

They provide a way to store multiple values in a single variable, rather than declaring separate variables for each value.

---

## Initialization and Usage (Java)

```java
class Main {
    public static void main(String[] args) {
        // Declaration aur Initialization (Fixed size = 5)
        int[] arr = new int[5];
        
        // Values assign karna
        arr[0] = 10;
        arr[1] = 20;
        arr[2] = 30;
        
        // Direct Array literal syntax
        int[] arr2 = {10, 20, 30, 40, 50};
        
        // Index se element access karna
        System.out.println(arr[1]); // Output: 20
    }
}
```

---

## Memory Representation

```text
Index:   0    1    2    3    4
       ------------------------
Data:  | 10 | 20 | 30 | 40 | 50 |
       ------------------------
Memory: 100  104  108  112  116   (Assuming 4 bytes per int)
```

---

## Key Characteristics

- **Fixed size**: Memory create karte waqt capacity define karni padti hai, jo baad mein resize nahi hoti.
- **Contiguous memory allocation**: Elements memory mein lagatar ek ke baad ek adjacent locations par store hote hain.
- **Homogeneous elements**: Sabhi elements ka data type same hona zaroori hai.
- **Zero-indexed**: Pehla element index `0` par aur last element index `n - 1` par hota hai.

---

## Advantages (Fayde)

- **Random Access**: Index ka use karke kisi bhi element ko direct $O(1)$ time complexity mein access kar sakte hain.
- **Memory Efficient**: Contiguous storage ki wajah se pointers maintain nahi karne padte (unlike Linked List).
- **Cache Friendliness**: Memory contiguous hone ke karan CPU cache locality acchi milti hai, jisse retrieval fast hota hai.
- Loops ke zariye iterate karna aur manipulate karna easy hota hai.

---

## Disadvantages (Nuksan)

- **Fixed Size**: Runtime par size badhaya ya ghataaya nahi ja sakta. Agar array fill ho jaye, toh naya bada array banakar items copy karne padte hain.
- **Slow Insertion/Deletion**: Middle ya start mein element insert ya delete karna slow ($O(N)$) hota hai kyunki baaki elements ko shift karna padta hai.
- **Memory Wastage**: Agar bada array declare kiya aur kam elements store kiye, toh baaki allocated memory waste ho jati hai.

---

## Applications (Kahan Use Hota Hai?)

- Fixed number of items store karne ke liye (jaise week ke days, months).
- Doosre data structures jaise Stacks, Queues, Heaps, aur Hash Tables ko implement karne mein.
- Matrices (2D Arrays) ya Lookup tables banane ke liye.
- Sorting aur Searching algorithms primary array par perform hote hain.

