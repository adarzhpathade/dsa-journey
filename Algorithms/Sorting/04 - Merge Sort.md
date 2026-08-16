# Merge Sort

#dsa #algorithms #sorting #java #divide_and_conquer

## 1. Formal Definition

**Merge Sort** is an efficient, stable, divide-and-conquer algorithm that recursively divides an array into two halves until each sub-array has one element, sorts them, and then merges the sorted halves back together.

## 2. "Explain like I'm 5" (Aasan Bhasha Mein)

Socho tumhare paas sort karne ke liye 100 exam test papers ka ek bada stack hai. Akale handle karna tough hai, toh tum stack ko aadha divide kar dete ho (50/50). Fir bhi bada hai, toh tum split karte jaate ho jab tak 1-1 test paper ka 100 piles na ban jaye. 1 paper ki pile toh pehle se sorted maani jayegi! Ab tum 1-1 wale do piles lete ho, compare karke unhe sorted 2-papers pile mein merge kar dete ho. Fir 2-2 wale piles ko merge karke 4-papers pile banate ho. Is tarah merging karte-karte tum end mein 100 papers ka ek single sorted stack taiyar kar lete ho.

**Merge Sort** ek "Divide and Conquer" algorithm hai. Yeh recursively array ko aadha todta jata hai jab tak single element na bache, aur fir unhe order mein wapas merge kar leta hai.

## 3. Real-Life Analogy

Cards ke ek bade deck ko 4 dosto ke saath milkar sort karna. Tum deck ko 4 chote parts mein divide karte ho, har dost ko ek part dete ho, unse unka part sort karate ho, aur fir end mein saare 4 sorted decks ko merge karke ek master sorted deck bana lete ho.

## 4. How it Works (Step-by-Step Logic)

1. **Divide:** Array ka midpoint nikalo aur use do halves mein break kar do.
2. **Conquer:** First half aur second half par recursively `mergeSort` call karo. Yeh tab tak divide karega jab tak sub-arrays ka size 1 na ho jaye.
3. **Merge:** Do sorted sub-arrays ko le kar ek single sorted array mein merge karo.
   - Merge karne ke liye dono sub-arrays ke pehle elements ko compare karo.
   - Chote element ko temporary array mein daalo.
   - Pointer aage badhao aur tab tak repeat karo jab tak dono sub-arrays fully merge na ho jayein.
   - Sorted temporary array ke elements ko original array mein copy kar do.

## 5. The Code (Java)

```java
import java.util.Arrays;

public class Main {
    
    // Main function jo arr[left...right] ko sort karta hai
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            // Middle point calculate karo
            int mid = left + (right - left) / 2;

            // First aur second halves ko sort karo
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            // Sorted halves ko merge karo
            merge(arr, left, mid, right);
        }
    }

    // arr[] ke do subarrays ko merge karta hai.
    // Pehla subarray hai arr[left..mid]
    // Dusra subarray hai arr[mid+1..right]
    private static void merge(int[] arr, int left, int mid, int right) {
        // Merge karne ke liye dono subarrays ka size nikalo
        int n1 = mid - left + 1;
        int n2 = right - mid;

        // Temporary arrays banao
        int[] L = new int[n1];
        int[] R = new int[n2];

        // Data temp arrays mein copy karo
        for (int i = 0; i < n1; ++i)
            L[i] = arr[left + i];
        for (int j = 0; j < n2; ++j)
            R[j] = arr[mid + 1 + j];

        // Temp arrays ko merge karo
        int i = 0, j = 0;
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

        // Agar L[] mein bache hue elements hain toh copy karo
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Agar R[] mein bache hue elements hain toh copy karo
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

## 6. Complexity Analysis (Interview Perspective)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(N \log N)$ | Yeh hamesha array ko half mein divide karta hai ($\log N$ steps) aur merge karne mein $O(N)$ time leta hai. |
| **Worst Case** | $O(N \log N)$ | Initial order chahe jo ho, exact wahi steps repeat hote hain. |
| **Average Case** | $O(N \log N)$ | Same as above. |

- **Space Complexity:** $O(N)$ kyunki merge process ke dauran temporary arrays (`L[]` aur `R[]`) ki zaroorat hoti hai. Yeh iska sabse bada limitation hai.

## 7. Kab Use Karein? (When to Use)

- Jab tumhein **guaranteed** $O(N \log N)$ time complexity chahiye aur worst-case risk afford nahi kar sakte (jaise Quick Sort mein hota hai).
- **Linked Lists** sort karne ke liye best algorithm hai kyunki Linked Lists mein random indexing nahi hoti aur Merge Sort ko random indexing ki zaroorat nahi padti.
- Java ke `Collections.sort()` mein objects sort karne ke liye use hota hai (Timsort hybrid algorithm Merge Sort par based hai) kyunki yeh stable sort hai.

## 8. Pros & Cons

**Pros:**
- Guaranteed $O(N \log N)$ time complexity har case mein.
- **Stable** sort hai (equal elements ka original relative order maintain rehta hai).
- Extremely large datasets ke liye fit hai jo single RAM memory mein fit nahi aate (External Sorting).

**Cons:**
- Temporary arrays ke liye $O(N)$ extra memory lagti hai.
- Small arrays ke liye recursive overhead ki wajah se Insertion Sort se thoda slow padta hai.

