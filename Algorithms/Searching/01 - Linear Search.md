Linear Search

#dsa #algorithms #searching #java

## 1. The "Explain like I'm 5" Definition

Imagine you have a stack of unorganized papers and you need to find a specific bill. You take the first paper, check if it's the bill. If not, you take the next one, and the next, until you find it or run out of papers. 

**Linear Search** is exactly this. It goes through a list one by one, from the beginning to the end, looking for a specific item.

## 2. Real-Life Analogy

Finding your friend in a crowded movie theater where there are no assigned seats. You look at the first person, then the second person, then the third, until you spot your friend.

## 3. How it Works (Step-by-Step)

1. Start at the very first element of the array (index 0).
2. Compare the current element with the target value you are looking for.
3. If they match, you found it! Return the index.
4. If they don't match, move to the next element.
5. Repeat steps 2-4 until you either find the target or reach the end of the array.
6. If you reach the end without finding it, return `-1` (meaning not found).

## 4. The Code (Java)

```java
public class Main {
    public static int linearSearch(int[] arr, int target) {
        // Loop through the entire array one by one
        for (int i = 0; i < arr.length; i++) {
            // Check if the current element matches the target
            if (arr[i] == target) {
                return i; // Found it, return the index
            }
        }
        return -1; // Exhausted the array, target not found
    }

    public static void main(String[] args) {
        int[] numbers = {10, 50, 30, 70, 80, 20, 90, 40};
        int target = 30;
        
        int resultIndex = linearSearch(numbers, target);
        
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
| **Best Case** | $O(1)$ | Target is the very first element. |
| **Worst Case** | $O(N)$ | Target is the last element or doesn't exist. You checked everything. |
| **Average Case** | $O(N)$ | Target is somewhere in the middle. |

- **Space Complexity:** $O(1)$ because it doesn't require any extra memory, just a few variables.

## 6. When to use it?

- When the array or list is **unsorted**. This is the only search algorithm you can use on completely random data without sorting it first.
- When the data set is very **small**. For tiny lists, the overhead of advanced algorithms isn't worth it.
- When you are searching in data structures that don't allow random access (like a basic Linked List where you *have* to go node by node anyway).

## 7. Pros & Cons

**Pros:**
- Super simple to understand and implement.
- Does not require the data to be sorted.
- Uses no extra memory.

**Cons:**
- Very slow for large datasets. It literally has to check every single item in the worst case.
