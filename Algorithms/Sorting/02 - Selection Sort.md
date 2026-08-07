Selection Sort

#dsa #algorithms #sorting #java

## 1. The "Explain like I'm 5" Definition

Imagine you have a messy shelf of books. To sort them, you look through every single book to find the thinnest one, and you place it at the very start of the shelf. Then, you look through the *remaining* books, find the next thinnest, and put it in the second spot. You repeat this until the shelf is sorted.

**Selection Sort** works by scanning the array to "select" the absolute smallest element, and then swapping it to the front. 

## 2. Real-Life Analogy

Picking a team for gym class. You scan the entire group to pick the fastest runner first. Then you scan the remaining group for the second fastest runner, and so on.

## 3. How it Works (Step-by-Step)

1. Start at index 0. This is the beginning of your "unsorted" portion.
2. Scan the entire array from index 0 to the end to find the minimum value.
3. Once found, swap this minimum value with the element at index 0. Now index 0 is "sorted".
4. Move your starting point to index 1. 
5. Scan from index 1 to the end to find the minimum of the *remaining* elements.
6. Swap it with the element at index 1.
7. Repeat this process, shifting the starting point one step to the right each time, until the whole array is sorted.

## 4. The Code (Java)

```java
import java.util.Arrays;

public class Main {
    public static void selectionSort(int[] arr) {
        int n = arr.length;

        // One by one move boundary of unsorted subarray
        for (int i = 0; i < n - 1; i++) {
            // Find the minimum element in unsorted array
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }

            // Swap the found minimum element with the first element of the unsorted part
            int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;
        }
    }

    public static void main(String[] args) {
        int[] numbers = {64, 25, 12, 22, 11};
        selectionSort(numbers);
        System.out.println("Sorted array: " + Arrays.toString(numbers));
    }
}
```

## 5. Complexity Analysis (The Interview Stuff)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(N^2)$ | Even if the array is already sorted, it still scans the remaining elements every single time to ensure it found the minimum. |
| **Worst Case** | $O(N^2)$ | Array is reverse sorted. |
| **Average Case** | $O(N^2)$ | Random data. |

- **Space Complexity:** $O(1)$ because it sorts in-place.

## 6. When to use it?

- When you are sorting on a system where memory write operations (swapping) are extremely expensive. Selection sort makes at most $O(N)$ swaps, whereas Bubble Sort and Insertion Sort can make $O(N^2)$ swaps. 
- Generally avoided for large lists due to its poor time complexity.

## 7. Pros & Cons

**Pros:**
- Simple to understand.
- Never makes more than $O(N)$ swaps, which is good if writing to memory is a bottleneck.
- In-place sorting ($O(1)$ space).

**Cons:**
- Always takes $O(N^2)$ time, even if the array is already perfectly sorted.
- Not a stable sort by default (meaning equal elements might swap relative positions).
