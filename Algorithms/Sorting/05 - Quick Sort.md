# Quick Sort

#dsa #algorithms #sorting #java #divide_and_conquer

## 1. Formal Definition

**Quick Sort** is an efficient divide-and-conquer sorting algorithm that selects a 'pivot' element, partitions the array around the pivot such that smaller elements move to the left and larger elements move to the right, and then recursively sorts the sub-arrays.

## 2. "Explain like I'm 5" (Aasan Bhasha Mein)

Socho tum logon ke ek group ko height ke according organize kar rahe ho. Tum kisi ek banda ko randomly pick karte ho (use hum "Pivot" bolenge). Tum Pivot se chote sabhi logon ko uske left side khada hone bolte ho aur Pivot se lambe logon ko right side. Ab Pivot apni exact correct final position par hai! Uske baad tum left group ko wahi same process unke aapas mein karne bolte ho, aur right group ko bhi wahi karne bolte ho.

**Quick Sort** ek "Divide and Conquer" algorithm hai. Yeh ek "pivot" element select karta hai aur array ko partition kar deta hai taaki sabhi chote elements left mein aur bade elements right mein aa jayein, aur fir left aur right halves par recursively yahi apply karta hai.

## 3. Real-Life Analogy

Apne closet (almirah) ko organize karna. Tum randomly ek shirt uthate ho (pivot). Is shirt se zyaada pehenne wali shirts ko tum left mein rakhte ho aur kam pehenne wali shirts ko right mein. Ab woh shirt bilkul perfect spot par hai. Tum left pile aur right pile ke liye yahi step repeat karte ho.

## 4. How it Works (Step-by-Step Logic)

1. **Pivot Select Karo:** Array se ek element ko pivot maano (commonly last element, first element, ya random element).
2. **Partitioning:** Array ko rearrange karo taaki:
   - Pivot se chote sabhi elements pivot ke pehle (left) aa jayein.
   - Pivot se bade sabhi elements pivot ke baad (right) aa jayein.
   - Pivot ab apni final sorted position par set ho jata hai.
3. **Recursion:** Left sub-array (pivot se chote) aur right sub-array (pivot se bade) par recursively upar wale steps apply karo.
4. Recursion ka base case 0 ya 1 size ka array hota hai, jo pehle se sorted hi maana jata hai.

## 5. The Code (Java)

```java
import java.util.Arrays;

public class Main {

    // QuickSort implement karne wala main function
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            // pi partitioning index hai, arr[pi] ab sahi jagah par hai
            int pi = partition(arr, low, high);

            // Partition ke pehle aur baad ke elements ko recursively sort karo
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    // Yeh function last element ko pivot manta hai, pivot ko sahi jagah par place karta hai,
    // aur chote elements left mein aur bade elements right mein set karta hai
    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high]; 
        int i = (low - 1); // chote element ka index
        
        for (int j = low; j < high; j++) {
            // Agar current element pivot se chota hai
            if (arr[j] < pivot) {
                i++;
                // arr[i] aur arr[j] ko swap karo
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        
        // arr[i+1] aur arr[high] (pivot) ko swap karo
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

## 6. Complexity Analysis (Interview Perspective)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(N \log N)$ | Choosed pivot hamesha exact median element hota hai, jisse array har baar perfectly aadha split hota hai. |
| **Worst Case** | $O(N^2)$ | Array pehle se sorted hai (ya reverse sorted) aur tum hamesha last element ko pivot banate ho. Har baar size sirf 1 se kam hota hai. |
| **Average Case** | $O(N \log N)$ | Average case mein pivot relatively evenly split kar deta hai. |

- **Space Complexity:** $O(\log N)$ recursive call stack space ke liye. Yeh in-place sort karta hai (Merge Sort ki tarah temporary arrays nahi lagte).

## 7. Kab Use Karein? (When to Use)

- **Lagbhag har jagah.** Ise sabse best general-purpose sorting algorithm mana jata hai.
- Java ke `Arrays.sort()` mein primitive types (`int`, `char`, etc.) sort karne ke liye use hota hai kyunki yeh extremely fast hai aur extra memory nahi leta.
- Jab high performance chahiye ho aur memory efficiency zaroori ho.

## 8. Pros & Cons

**Pros:**
- Practice mein extremely fast ($O(N \log N)$ category mein cache locality acchi hone ki wajah se often Merge Sort se bhi tez hota hai).
- In-place sorting ($O(\log N)$ extra space stack ke liye).

**Cons:**
- Worst-case time complexity $O(N^2)$ ho sakti hai (halanki random pivot choice se ise avoid kiya ja sakta hai).
- **Stable sort nahi hai** (equal elements relative position switch kar sakte hain).

