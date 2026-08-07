Bubble Sort

#dsa #algorithms #sorting #java

## 1. The "Explain like I'm 5" Definition

Imagine you have a line of students of different heights, and you want to arrange them from shortest to tallest. You start at the beginning and look at the first two students. If the left one is taller than the right one, you swap them. Then you move one step right and do it again. You keep doing this over and over until the tallest students "bubble up" to the end of the line.

**Bubble Sort** works by repeatedly swapping adjacent elements if they are in the wrong order. 

## 2. Real-Life Analogy

Sorting a hand of playing cards by looking at just two cards at a time, left to right, and swapping them if the left card is bigger. The biggest cards slowly drift to the right side of your hand.

## 3. How it Works (Step-by-Step)

1. Start at index 0. Compare the element at index 0 with index 1.
2. If `arr[0] > arr[1]`, swap them.
3. Move to the next pair (`arr[1]` and `arr[2]`). Swap if needed.
4. Continue this until the end of the array. After this first full pass, the **largest element is guaranteed to be at the very end**.
5. Repeat the whole process for the remaining unsorted portion of the array (you don't need to check the last element anymore).
6. Keep repeating until you make a full pass without doing any swaps (which means it's sorted).

## 4. The Code (Java)

```java
import java.util.Arrays;

public class Main {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        boolean swapped;
        
        for (int i = 0; i < n - 1; i++) {
            swapped = false;
            // The last i elements are already in place, so we don't check them
            for (int j = 0; j < n - i - 1; j++) {
                // If the current element is greater than the next, swap them
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }
            // If no two elements were swapped by inner loop, then array is sorted
            if (!swapped) {
                break;
            }
        }
    }

    public static void main(String[] args) {
        int[] numbers = {64, 34, 25, 12, 22, 11, 90};
        bubbleSort(numbers);
        System.out.println("Sorted array: " + Arrays.toString(numbers));
    }
}
```

## 5. Complexity Analysis (The Interview Stuff)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(N)$ | The array is already sorted. The algorithm detects this on the first pass (because of the `swapped` boolean). |
| **Worst Case** | $O(N^2)$ | The array is reverse sorted. Every single element needs to be swapped. |
| **Average Case** | $O(N^2)$ | The array has random elements. |

- **Space Complexity:** $O(1)$ because it sorts the array in place, requiring only a single variable (`temp`) for swapping.

## 6. When to use it?

- **Almost Never** in production software. It is generally too slow.
- It is primarily used as an educational tool to introduce the concept of sorting algorithms because it is so easy to conceptualize.
- Can be used if the array is *already almost sorted* (where it achieves $O(N)$), but Insertion Sort is usually better for that.

## 7. Pros & Cons

**Pros:**
- Extremely easy to understand and code.
- Does not require any extra memory (in-place sorting).
- Stable sorting algorithm (meaning equal elements retain their relative order).

**Cons:**
- Very inefficient for large datasets.
- Considered one of the slowest sorting algorithms.
