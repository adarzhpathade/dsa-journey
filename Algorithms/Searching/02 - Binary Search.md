# Binary Search

#dsa #algorithms #searching #java

## 1. Formal Definition

**Binary Search** is an efficient search algorithm that works on a sorted array by repeatedly dividing the search space in half until the target element is found or the search space becomes empty.

## 2. "Explain like I'm 5" (Aasan Bhasha Mein)

Socho tum 1 se 100 ke beech ek number guess kar rahe ho aur main tumhein batanewala hu ki tumhara guess "too high" hai ya "too low". Tum pehle 1, 2, 3 guess nahi karoge. Tum 50 guess karoge! Agar main kahun "too high", toh tumhein pata chal jayega ki answer 1 se 49 ke beech hai. Agli baar tum 25 guess karoge. Is tarah tum har baar options ko aadha (half) kar dete ho.

**Binary Search** bilkul yahi karta hai. Yeh ek **sorted** list mein har baar search area ko half mein divide karke element dhundta hai.

## 3. Real-Life Analogy

Dictionary mein word dhundna. Tum dictionary ka page 1, 2, 3 turn nahi karte. Tum roughly middle se dictionary kholte ho. Agar tum "Zebra" dhund rahe ho aur page par "Monkey" nikla, toh tum pehla half poora ignore kar dete ho aur remaining pages ko fir se divide karke search karte ho.

## 4. How it Works (Step-by-Step Logic)

*Note: Yeh algorithm kaam kare iske liye array ka **sorted** hona zaroori hai.*

1. Do pointers banao: `start` ko beginning index `0` par rakho aur `end` ko last index par.
2. Middle index calculate karo: `mid = start + (end - start) / 2`.
3. `mid` position wale element ko target value se compare karo.
4. **Match:** Agar `arr[mid] == target`, toh element mil gaya! Return `mid`.
5. **Target Chota Hai:** Agar target `arr[mid]` se chota hai, toh woh left half mein hoga. Pointer update karo: `end = mid - 1`.
6. **Target Bada Hai:** Agar target `arr[mid]` se bada hai, toh woh right half mein hoga. Pointer update karo: `start = mid + 1`.
7. Yeh steps tab tak repeat karo jab tak `start <= end` rahe. Agar `start > end` ho gaya, matlab element array mein nahi hai (`return -1`).

## 5. The Code (Java)

```java
public class Main {
    public static int binarySearch(int[] arr, int target) {
        int start = 0;
        int end = arr.length - 1;

        while (start <= end) {
            // Integer overflow se bachne ke liye safe mid calculation
            int mid = start + (end - start) / 2;

            if (arr[mid] == target) {
                return mid; // Target mil gaya!
            } else if (arr[mid] < target) {
                // Target right half mein hai, left half ignore karo
                start = mid + 1;
            } else {
                // Target left half mein hai, right half ignore karo
                end = mid - 1;
            }
        }
        return -1; // Target nahi mila
    }

    public static void main(String[] args) {
        // ARRAY MUST BE SORTED!
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

## 6. Complexity Analysis (Interview Perspective)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(1)$ | Target pehli hi baari mein exact `mid` par mil gaya. |
| **Worst Case** | $O(\log N)$ | Target end tak nahi milta ya last step par milta hai. Array har step par aadha hota gaya. |
| **Average Case** | $O(\log N)$ | Target split hote hote beech mein mil gaya. |

- **Space Complexity:** $O(1)$ iterative approach ke liye (bas kuch pointer variables use hote hain). Recursive approach mein function call stack ki wajah se $O(\log N)$ space lagta hai.

## 7. Kab Use Karein? (When to Use)

- **Jab data SORTED ho.** Yeh mandatory rule hai.
- Jab bade datasets ke saath kaam kar rahe ho. Binary Search super fast hai—10 lakh (1 million) elements ko yeh lagbhag ~20 steps mein search kar leta hai.
- Problems jahan first/last occurrence find karni ho ya perfect square root nikalna ho.

## 8. Pros & Cons

**Pros:**
- Bade sorted datasets ke liye extremely fast ($O(\log N)$ process $O(N)$ se bahut behter hai).
- Memory efficient.

**Cons:**
- Array ka strictly sorted hona zaroori hai. Data sort karne mein $O(N \log N)$ time lagta hai; isliye agar sirf 1 baar search karna ho toh direct Linear Search better hota hai.
- Linked list jaise data structures par directly apply nahi hota jahan fast random indexing allow nahi hoti.

