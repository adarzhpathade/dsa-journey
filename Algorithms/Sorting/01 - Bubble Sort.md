# Bubble Sort

#dsa #algorithms #sorting #java

## 1. Formal Definition

**Bubble Sort** is a simple comparison-based sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order until the list is sorted.

## 2. "Explain like I'm 5" (Aasan Bhasha Mein)

Socho tumhare paas alag-alag heights ke students ki ek line hai, aur tumhein unhe sabse chote se sabse lambe (shortest to tallest) arrange karna hai. Tum pehle do students ko dekhoge. Agar left wala student right wale se lamba hai, toh tum unhe swap kar doge. Fir tum ek step aage badhoge aur wahi repeat karoge. Yeh process baar-baar repeat hoga jab tak sabse lambe students "bubble up" karke line ke end tak na pahunch jayein.

**Bubble Sort** adjacent (pass wale) elements ko baar-baar swap karke sahi order mein lata hai.

## 3. Real-Life Analogy

Playing cards ke haath ko sort karna. Tum ek baar mein bas do adjacent cards ko dekhte ho (left to right), aur agar left wala card bada hai toh unhe swap kar dete ho. Bada card dhire-dhire right side shift hota jata hai.

## 4. How it Works (Step-by-Step Logic)

1. Index 0 se start karo. Index 0 aur Index 1 ke elements ko compare karo.
2. Agar `arr[0] > arr[1]`, toh unhe swap kar do.
3. Agle pair par move karo (`arr[1]` aur `arr[2]`). Zaroorat padne par swap karo.
4. Array ke end tak yeh karte jao. Pehle poore pass ke baad, **sabse bada element guarantee ke saath array ke bilkul end par pahunch jata hai**.
5. Baaki bache unsorted part ke liye poora process repeat karo (ab last element check karne ki zaroorat nahi hai).
6. Yeh tab tak repeat karte raho jab tak ek aisa pass na nikal jaye jisme koi swap na hua ho (iska matlab array completely sort ho chuka hai).

## 5. The Code (Java)

```java
import java.util.Arrays;

public class Main {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        boolean swapped;
        
        for (int i = 0; i < n - 1; i++) {
            swapped = false;
            // Last i elements pehle se hi sorted position mein hain
            for (int j = 0; j < n - i - 1; j++) {
                // Agar current element agle element se bada hai, swap karo
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }
            // Agar inner loop mein koi swap nahi hua, toh array already sorted hai
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

## 6. Complexity Analysis (Interview Perspective)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(N)$ | Array pehle se sorted hai. Algortihm ko `swapped` boolean flag ki madad se pehle pass mein hi pata chal jata hai. |
| **Worst Case** | $O(N^2)$ | Array reverse sorted hai. Har ek element ko swap karna padega. |
| **Average Case** | $O(N^2)$ | Array mein random unsorted elements hain. |

- **Space Complexity:** $O(1)$ kyunki yeh array ko in-place sort karta hai, sirf ek `temp` variable swapping ke liye chahiye hota hai.

## 7. Kab Use Karein? (When to Use)

- Production software mein **lagbhag kabhi nahi**. Yeh bahut slow hai.
- Mainly sorting algorithms ke basics samajhne ke liye use hota hai kyunki iska concept visualized karna bahut aasan hai.
- Agar array *lagbhag sorted* ho tab use kar sakte hain ($O(N)$ achieve karta hai), lekin wahan bhi Insertion Sort behter perform karta hai.

## 8. Pros & Cons

**Pros:**
- Code karne aur samajhne mein super easy.
- Koi extra memory ki zaroorat nahi ($O(1)$ space).
- Stable sorting algorithm hai (equal elements ka relative order change nahi hota).

**Cons:**
- Bade datasets ke liye extremely inefficient hai.
- Sabse slow sorting algorithms mein se ek mana jata hai.

