Binary Search

#dsa #algorithms #searching #java

## 1. The "Explain like I'm 5" Definition

Imagine you're trying to guess a number between 1 and 100, and I'll tell you if your guess is "too high" or "too low". You wouldn't guess 1, then 2, then 3. You'd guess 50. If I say "too high", you know the answer is between 1 and 49. Next you guess 25, cutting the options in half every single time.

**Binary Search** does exactly this. It finds an item in a **sorted** list by repeatedly dividing the search area in half.

## 2. Real-Life Analogy

Finding a word in a dictionary. You don't flip through page 1, page 2, page 3. You open the dictionary roughly in the middle. If you're looking for "Zebra" and you land on "Monkey", you know you can completely ignore the entire first half of the dictionary. You keep splitting the remaining pages until you find your word.

## 3. How it Works (Step-by-Step)

*Note: The array **must** be sorted for this to work.*

1. Set two pointers: `start` at the beginning (index 0) and `end` at the last index.
2. Calculate the `mid` index: `(start + end) / 2`.
3. Compare the element at the `mid` index with the target value.
4. **Match:** If it equals the target, return `mid`.
5. **Target is Smaller:** If the target is less than the `mid` element, it must be in the left half. Move the `end` pointer to `mid - 1`.
6. **Target is Larger:** If the target is greater than the `mid` element, it must be in the right half. Move the `start` pointer to `mid + 1`.
7. Repeat until `start` is greater than `end`. If that happens, the target isn't there (return `-1`).

## 4. The Code (Java)

```java
public class Main {
    public static int binarySearch(int[] arr, int target) {
        int start = 0;
        int end = arr.length - 1;

        while (start <= end) {
            // A safer way to find mid that prevents integer overflow for huge arrays
            int mid = start + (end - start) / 2;

            if (arr[mid] == target) {
                return mid; // Found it!
            } else if (arr[mid] < target) {
                // Target is in the right half, ignore the left half
                start = mid + 1;
            } else {
                // Target is in the left half, ignore the right half
                end = mid - 1;
            }
        }
        return -1; // Target not found
    }

    public static void main(String[] args) {
        // MUST BE SORTED!
        int[] sortedNumbers = {10, 20, 30, 40, 50, 60, 70, 80, 90};
        int target = 70;
        
        int resultIndex = binarySearch(sortedNumbers, target);
        
        if (resultIndex != -1) {
            System.out.println("Element found at index: " + resultIndex);
        } else {
            System.out.println("Element not found in the array.");
        }
    }
}
```

## 5. Complexity Analysis (The Interview Stuff)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(1)$ | Target is exactly in the middle on the first try. |
| **Worst Case** | $O(\log N)$ | Target is at the very end or doesn't exist. The array is halved repeatedly. |
| **Average Case** | $O(\log N)$ | Target is found somewhere in the middle splits. |

- **Space Complexity:** $O(1)$ for the iterative approach shown above (only uses a few pointer variables). $O(\log N)$ if implemented recursively due to the call stack.

## 6. When to use it?

- **When the data is SORTED.** This is an absolute requirement.
- When dealing with large datasets. Binary Search is incredibly fast; it can search a million items in just ~20 steps.
- Great for problems like finding the first/last occurrence of a number, or finding the square root of a number efficiently.

## 7. Pros & Cons

**Pros:**
- Extremely fast for large, sorted datasets ($O(\log N)$ is vastly superior to $O(N)$).
- Memory efficient.

**Cons:**
- Requires the data to be perfectly sorted beforehand. Sorting data takes $O(N \log N)$ time, so if you only need to search *once*, sorting it just to use Binary Search is actually slower than just doing a Linear Search!
- Not directly applicable to data structures that don't allow fast random access (like standard Linked Lists).
