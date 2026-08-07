Merge Sort

#dsa #algorithms #sorting #java #divide_and_conquer

## 1. The "Explain like I'm 5" Definition

Imagine you have a giant stack of 100 tests to sort by grade. It's overwhelming. So, you split the stack in half (50/50). Still too big. You keep splitting them until you have 100 piles of exactly 1 test each. A pile of 1 is technically sorted! Now, you take two piles of 1, compare them, and combine them into a sorted pile of 2. You take two piles of 2, combine them into a sorted pile of 4. You keep merging them back up until you have one giant sorted stack of 100.

**Merge Sort** is a "Divide and Conquer" algorithm. It recursively breaks an array in half until each half has only 1 element, and then merges those halves back together in sorted order.

## 2. Real-Life Analogy

Sorting a massive deck of cards by having 4 friends help. You divide the deck into 4 smaller decks, give one to each friend, have them sort their small deck, and then you collect them and merge the 4 sorted decks together.

## 3. How it Works (Step-by-Step)

1. **Divide:** Find the middle point of the array and divide it into two halves.
2. **Conquer:** Recursively call Merge Sort on the first half and the second half. This keeps dividing the array until the sub-arrays have a size of 1.
3. **Merge:** Take two sorted sub-arrays and merge them into a single sorted array. 
   - To merge, you compare the first element of both sub-arrays.
   - Put the smaller one into a new temporary array.
   - Move the pointer forward and repeat until both sub-arrays are fully merged.
   - Copy the sorted temporary array back into the original array.

## 4. The Code (Java)

```java
import java.util.Arrays;

public class Main {
    
    // Main function that sorts arr[left...right]
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            // Find the middle point
            int mid = left + (right - left) / 2;

            // Sort first and second halves
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            // Merge the sorted halves
            merge(arr, left, mid, right);
        }
    }

    // Merges two subarrays of arr[].
    // First subarray is arr[left..mid]
    // Second subarray is arr[mid+1..right]
    private static void merge(int[] arr, int left, int mid, int right) {
        // Find sizes of two subarrays to be merged
        int n1 = mid - left + 1;
        int n2 = right - mid;

        // Create temp arrays
        int[] L = new int[n1];
        int[] R = new int[n2];

        // Copy data to temp arrays
        for (int i = 0; i < n1; ++i)
            L[i] = arr[left + i];
        for (int j = 0; j < n2; ++j)
            R[j] = arr[mid + 1 + j];

        // Merge the temp arrays

        // Initial indexes of first and second subarrays
        int i = 0, j = 0;

        // Initial index of merged subarray array
        int k = left;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }

        // Copy remaining elements of L[] if any
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Copy remaining elements of R[] if any
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }

    public static void main(String[] args) {
        int[] numbers = {12, 11, 13, 5, 6, 7};
        mergeSort(numbers, 0, numbers.length - 1);
        System.out.println("Sorted array: " + Arrays.toString(numbers));
    }
}
```

## 5. Complexity Analysis (The Interview Stuff)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(N \log N)$ | It always divides the array in half ($\log N$ steps) and takes $O(N)$ time to merge them back. |
| **Worst Case** | $O(N \log N)$ | Same as above. It does exactly the same amount of work regardless of the initial order. |
| **Average Case** | $O(N \log N)$ | Same as above. |

- **Space Complexity:** $O(N)$ because it requires temporary arrays (`L[]` and `R[]`) during the merge process. This is its biggest drawback.

## 6. When to use it?

- When you need a **guaranteed** $O(N \log N)$ time complexity and can't risk a worst-case scenario (like in Quick Sort).
- Great for sorting **Linked Lists** because linked lists don't have random access, and merging doesn't require random access (unlike Quick Sort which needs to swap elements all over the place).
- Used in Java's `Collections.sort()` for objects (it uses a hybrid called Timsort, which relies heavily on Merge Sort) because it is a stable sort.

## 7. Pros & Cons

**Pros:**
- Excellent, guaranteed time complexity of $O(N \log N)$ in all cases.
- It is a **stable** sort (equal elements maintain relative order).
- Great for massive datasets that don't fit into memory (External Sorting).

**Cons:**
- Requires $O(N)$ extra memory for the temporary arrays.
- Overkill for small arrays (slower than Insertion sort due to recursive overhead).
