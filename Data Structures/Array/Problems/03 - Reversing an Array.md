# Reversing an Array

#dsa #java #array

> **Concept:** [[Arrays]]

## Problem Statement

Reverse the elements of an **Array** in-place.

---

## Approach (Two-Pointer Technique)

- Do pointers use karo: `start` ko index `0` par aur `end` ko last index (`arr.length - 1`) par set karo.
- `start` aur `end` indices par rakhe elements ko swap karo.
- `start` ko increment (`start++`) karo aur `end` ko decrement (`end--`) karo.
- Is process ko repeat karte raho jab tak `start < end` rahe.

---

## Code (Java)

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        
        int start = 0;
        int end = arr.length - 1;

        while (start < end) {
            // Swap logic
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;

            start++;
            end--;
        }

        System.out.println(Arrays.toString(arr));
    }
}
```

---

## Output

```text
[50, 40, 30, 20, 10]
```

---

## Time & Space Complexity

| Operation | Complexity |
|-----------|------------|
| Reversing | $O(N)$ |
| Auxiliary Space | $O(1)$ |

---

## Key Points (Khaas Baatein)

- In-place reversal karne se memory space bachta hai kyunki extra array create nahi karna padta.
- Two-pointer approach is problem ko solve karne ka sabse optimal tarika hai.

