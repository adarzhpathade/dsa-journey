Quick Sort

#dsa #algorithms #sorting #java #divide_and_conquer

## 1. The "Explain like I'm 5" Definition

Imagine you are organizing a group of people by height. You randomly pick one person (let's call them the "Pivot"). You tell everyone shorter than the Pivot to stand on the left, and everyone taller to stand on the right. Now, the Pivot is perfectly in their correct spot! Then, you tell the left group to do the exact same thing amongst themselves, and the right group to do the exact same thing. 

**Quick Sort** is a "Divide and Conquer" algorithm. It picks a "pivot" element and partitions the array so everything smaller is on the left and everything larger is on the right, then recursively does this for the left and right halves.

## 2. Real-Life Analogy

Organizing your closet. You grab a random shirt (the pivot). You put all shirts you wear more often than this one on the left, and all shirts you wear less often on the right. Now that shirt is in the perfect spot. You repeat this for the left pile and the right pile.

## 3. How it Works (Step-by-Step)

1. **Pick a Pivot:** Choose an element from the array to be the pivot (often the last element, the first element, or a random element).
2. **Partition:** Rearrange the array so that:
   - All elements less than the pivot are placed before it.
   - All elements greater than the pivot are placed after it.
   - The pivot is now in its final, sorted position.
3. **Recursion:** Recursively apply the above steps to the sub-array of elements with smaller values (left of the pivot) and the sub-array of elements with greater values (right of the pivot).
4. The base case for recursion is an array of size 0 or 1, which is already sorted.

## 4. The Code (Java)

```java
import java.util.Arrays;

public class Main {

    // Main function that implements QuickSort
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            // pi is partitioning index, arr[pi] is now at right place
            int pi = partition(arr, low, high);

            // Recursively sort elements before partition and after partition
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    // This function takes last element as pivot, places the pivot element at its 
    // correct position in sorted array, and places all smaller to left of pivot 
    // and all greater elements to right of pivot
    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high]; 
        int i = (low - 1); // index of smaller element
        
        for (int j = low; j < high; j++) {
            // If current element is smaller than the pivot
            if (arr[j] < pivot) {
                i++;
                // swap arr[i] and arr[j]
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        
        // swap arr[i+1] and arr[high] (or pivot)
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;

        return i + 1;
    }

    public static void main(String[] args) {
        int[] numbers = {10, 7, 8, 9, 1, 5};
        quickSort(numbers, 0, numbers.length - 1);
        System.out.println("Sorted array: " + Arrays.toString(numbers));
    }
}
```

## 5. Complexity Analysis (The Interview Stuff)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(N \log N)$ | The pivot picked always happens to be the exact median, splitting the array perfectly in half every time. |
| **Worst Case** | $O(N^2)$ | The array is already sorted (or reverse sorted) and you always pick the last element as the pivot. It only reduces the array size by 1 each time. |
| **Average Case** | $O(N \log N)$ | On average, the pivot splits the array relatively evenly. |

- **Space Complexity:** $O(\log N)$ due to the recursive call stack space. It sorts in-place (no temporary arrays like Merge Sort).

## 6. When to use it?

- **Almost everywhere.** It is widely considered the best general-purpose sorting algorithm.
- Used in Java's `Arrays.sort()` for primitives (`int`, `char`, etc.) because it's extremely fast and doesn't require extra memory.
- When you need high performance and memory is a concern (since it's in-place).

## 7. Pros & Cons

**Pros:**
- Extremely fast in practice (often faster than Merge Sort because it has better cache locality).
- Sorts in-place, meaning it uses very little extra memory ($O(\log N)$).

**Cons:**
- Worst-case time complexity is $O(N^2)$ (though this can be mitigated by picking a random pivot).
- It is **not stable** (equal elements might swap relative positions).
