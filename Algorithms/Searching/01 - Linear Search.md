# Linear Search

#dsa #algorithms #searching #java

## 1. Formal Definition

**Linear Search** is a sequential search algorithm that starts from the first element of a collection and checks each element one by one until the target value is found or the end of the collection is reached.

## 2. "Explain like I'm 5" (Aasan Bhasha Mein)

Socho tumhare paas ek bina arrange kiye hue papers ka bundle hai aur tumhein ek specific bill dhundna hai. Tum pehla paper check karoge, agar woh bill nahi hai toh agla check karoge, aur tab tak karte rahoge jab tak bill mil na jaye ya papers khatam na ho jayein.

**Linear Search** bilkul yahi karta hai. Yeh list ke pehle element se shuru karke last element tak ek-ek karke target item ko search karta hai.

## 3. Real-Life Analogy

Ek crowded movie theater mein jahan assigned seats nahi hain, wahan apne dost ko dhundna. Tum pehle banda dekhoge, fir dusra, fir teesra... jab tak dost dikh na jaye.

## 4. How it Works (Step-by-Step Logic)

1. Array ke sabse pehle element (index 0) se start karo.
2. Current element ko apne target value se compare karo.
3. Agar match ho gaya, toh element mil gaya! Uska index return kar do.
4. Agar match nahi hua, toh agle element par move kar jao.
5. Steps 2-4 ko tab tak repeat karo jab tak target na mil jaye ya array khatam na ho jaye.
6. Agar poora array check karne par bhi target nahi milta, toh `-1` return kar do (matlab element array mein nahi hai).

## 5. The Code (Java)

```java
public class Main {
    public static int linearSearch(int[] arr, int target) {
        // Poore array par ek-ek karke loop chalao
        for (int i = 0; i < arr.length; i++) {
            // Check karo kya current element target ke barabar hai
            if (arr[i] == target) {
                return i; // Element mil gaya, index return kar do
            }
        }
        return -1; // Poora array search ho gaya, target nahi mila
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

## 6. Complexity Analysis (Interview Perspective)

| Scenario | Time Complexity | Explanation |
| :--- | :--- | :--- |
| **Best Case** | $O(1)$ | Target exact pehle element (index 0) par mil gaya. |
| **Worst Case** | $O(N)$ | Target last element par hai ya array mein majood hi nahi hai. Poora array check karna pada. |
| **Average Case** | $O(N)$ | Target array ke beech mein kahin milta hai. |

- **Space Complexity:** $O(1)$ kyunki isme koi extra memory allocate nahi hoti, bas ek-do pointer variables use hote hain.

## 7. Kab Use Karein? (When to Use)

- Jab array ya list **unsorted** ho. Unsorted data par sorting kiye bina yeh akela simple search technique hai.
- Jab dataset bahut **chota (small)** ho. Chote data ke liye complex algorithms setup karne ki zarurat nahi hoti.
- Jab kisi aise data structure mein search kar rahe ho jahan random access allow nahi hota (jaise standard Linked List jahan node-by-node hi traverse karna padta hai).

## 8. Pros & Cons

**Pros:**
- Samajhne aur code karne mein super simple hai.
- Data ka sorted hona zaroori nahi hai.
- Koi extra memory consume nahi karta.

**Cons:**
- Bade datasets ke liye bahut slow hai kyunki worst case mein har element check karna padta hai.

