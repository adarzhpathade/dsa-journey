# Selection Sort

#dsa #algorithms #sorting #java

## 1. Formal Definition

**Selection Sort** is an in-place comparison sorting algorithm that divides the array into a sorted and an unsorted region, repeatedly selecting the smallest element from the unsorted region and moving it to the end of the sorted region.

## 2. "Explain like I'm 5" (Aasan Bhasha Mein)

Socho tumhare paas books ki ek bikhari hui shelf hai. Unhe sort karne ke liye tum poori shelf par har ek book check karte ho aur sabse thinnest (patli) book dhoondh kar sabse pehle spot par rakh dete ho. Phir tum *bachi hui* books mein se next thinnest book dhundhte ho aur use second spot par rakh dete ho. Tum tab tak yahi karte rehte ho jab tak poori shelf sort na ho jaye.

**Selection Sort** poore array ko scan karke absolute smallest element ko "select" karta hai aur use front par swap kar deta hai.

## 3. Real-Life Analogy

Gym class mein team choose karna. Tum poore group ko scan karke sabse fast runner ko pehle pick karte ho. Phir bache hue group ko scan karke second fastest runner ko pick karte ho, aur aage bhi aisa hi karte ho.

## 4. How it Works (Step-by-Step Logic)

1. Index 0 se start karo. Yeh tumhare "unsorted" portion ka beginning point hai.
2. Index 0 se end tak poore array ko scan karo minimum value dhoondhne ke liye.
3. Jab minimum value mil jaye, use index 0 wale element ke saath swap kar do. Ab index 0 "sorted" ho gaya.
4. Apne starting point ko index 1 par shift karo.
5. Index 1 se end tak scan karke *remaining* elements mein se minimum dhoondho.
6. Use index 1 wale element ke saath swap kar do.
7. Is process ko repeat karo, har baar starting point ko ek step right shift karte jao, jab tak poora array sort na ho jaye.

## 5. The Code (Java)

```java
import java.util.Arrays;

public class Main {
    public static void selectionSort(int[] arr) {
        int n = arr.length;

        // Unsorted subarray ki boundary ek-ek karke aage badhao
        for (int i = 0; i < n - 1; i++) {
            // Unsorted array mein minimum element dhoondho
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }

            // Dhoondhe gaye minimum element ko unsorted part ke pehle element se swap karo
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

## 6. Complexity Analysis (Interview Perspective)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(N^2)$ | Array agar pehle se sorted bhi ho, tab bhi yeh har baar remaining elements ko scan karke minimum confirm karta hai. |
| **Worst Case** | $O(N^2)$ | Array reverse sorted ho. |
| **Average Case** | $O(N^2)$ | Random unsorted data. |

- **Space Complexity:** $O(1)$ kyunki in-place sorting karta hai.

## 7. Kab Use Karein? (When to Use)

- Jab tum kisi aise system par sorting kar rahe ho jahan memory write operations (swapping) bahut expensive hote hain. Selection sort maximum $O(N)$ swaps karta hai, jabki Bubble Sort aur Insertion Sort $O(N^2)$ swaps kar sakte hain.
- Poor time complexity ki wajah se bade lists ke liye ise avoid hi kiya jata hai.

## 8. Pros & Cons

**Pros:**
- Samajhne mein simple hai.
- Kabhi bhi $O(N)$ se zyaada swaps nahi karta, jo memory writing cost kam karne ke liye accha hai.
- In-place sorting ($O(1)$ space).

**Cons:**
- Hamesha $O(N^2)$ time leta hai, chahe array pehle se perfectly sorted hi kyun na ho.
- By default stable sort nahi hota (equal elements relative position change kar sakte hain).

