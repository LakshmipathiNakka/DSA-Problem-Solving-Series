# 🚀 Second Largest Element

> 📚 **DSA Problem Solving Series by @techno_pathy**  
> 🧠 **Technique:** Single Pass Traversal  
> 📊 **Difficulty:** Easy  
> 🏷 **Topic:** Arrays

---

## 📌 Problem Statement

You are given an array of integers.

Your task is to **find the second largest element in the array**.

The solution should run in **O(n)** time **without sorting the array**.

---

## 🧾 Example

**Input**

```
6
4 5 7 10 10 8
```

**Output**

```
8
```

### 🔎 Explanation

We traverse the array while maintaining two variables:

- `max` → largest element found so far
- `second` → second largest element

Initial values

```
max = 4
second = -1
```

Step 1 → element = 5

```
5 > 4
second = 4
max = 5
```

Step 2 → element = 7

```
7 > 5
second = 5
max = 7
```

Step 3 → element = 10

```
10 > 7
second = 7
max = 10
```

Step 4 → element = 10

```
duplicate of max
ignore
```

Step 5 → element = 8

```
8 < max (10) AND 8 > second (7)

second = 8
```

### ✅ Final Result

```
Second Largest = 8
```

---

## 💡 Key Idea — Single Pass Traversal

Instead of sorting the array, we track two values while traversing the array once.

| Variable | Role |
|--------|------|
| `max` | stores the largest element |
| `second` | stores the second largest element |

### Rules

If `arr[i] > max`

```
second = max
max = arr[i]
```

If `arr[i] > second` AND `arr[i] < max`

```
second = arr[i]
```

---

## 🧩 Pseudocode

```
function secondLargest(arr, n):

    max = arr[0]
    second = -1

    for i from 1 to n-1:

        if arr[i] > max:
            second = max
            max = arr[i]

        else if arr[i] > second AND arr[i] < max:
            second = arr[i]

    return second
```

---

## 💻 Code Implementation

### 🧩 C++

```cpp
#include <bits/stdc++.h>
using namespace std;

int secondLargest(int arr[], int n) {

    int maxVal = arr[0];
    int second = -1;

    for(int i = 1; i < n; i++) {

        if(arr[i] > maxVal) {
            second = maxVal;
            maxVal = arr[i];
        }

        else if(arr[i] > second && arr[i] < maxVal) {
            second = arr[i];
        }

    }

    return second;
}

int main() {

    int arr[] = {4,5,7,10,10,8};
    int n = sizeof(arr)/sizeof(arr[0]);

    cout << secondLargest(arr, n);
}
```

---

### 🐍 Python

```python
def second_largest(arr):

    max_val = arr[0]
    second = -1

    for i in range(1, len(arr)):

        if arr[i] > max_val:
            second = max_val
            max_val = arr[i]

        elif arr[i] > second and arr[i] < max_val:
            second = arr[i]

    return second


arr = [4,5,7,10,10,8]

print(second_largest(arr))
```

---

### ☕ Java

```java
class SecondLargest {

    static int secondLargest(int arr[]) {

        int max = arr[0];
        int second = -1;

        for(int i = 1; i < arr.length; i++) {

            if(arr[i] > max) {
                second = max;
                max = arr[i];
            }

            else if(arr[i] > second && arr[i] < max) {
                second = arr[i];
            }

        }

        return second;
    }

    public static void main(String[] args) {

        int arr[] = {4,5,7,10,10,8};

        System.out.println(secondLargest(arr));
    }

}
```

---

## ⏱ Complexity Analysis

| Metric | Complexity |
|------|-------------|
| Time Complexity | **O(n)** |
| Space Complexity | **O(1)** |

✔ Only **one traversal** of the array  
✔ **No sorting required**

---

## 🎯 Key Takeaways

- Avoid sorting (**O(n log n)**)
- Track **largest and second largest simultaneously**
- Solve in **single traversal**
- Common **coding interview question**

---

⭐ **Created for learning by @techno_pathy**
