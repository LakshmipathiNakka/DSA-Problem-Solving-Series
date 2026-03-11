# 🚀 Move Zeros To End

> 📚 **DSA Problem Solving Series by @techno_pathy**  
> 🧠 **Technique:** Two Pointer  
> 🔗 **LeetCode Problem:** https://leetcode.com/problems/move-zeroes/  
> 📊 **Difficulty:** Easy  
> 🏷 **Topic:** Arrays, Two Pointers

---

## 📌 Problem Statement

You are given an array of integers.

The task is to **move all zeros to the end of the array** while **maintaining the order of non-zero elements**.

The solution must run in **O(n) time** and **O(1) space**.

---

## 🧾 Example

**Input**

```
9
0 0 3 0 0 5 0 0 7
```

**Output**

```
3 5 7 0 0 0 0 0 0
```

---

## 💡 Key Idea — Two Pointer Technique

We maintain **two pointers**.

| Pointer | Role |
|--------|------|
| `i` | scans the array |
| `j` | next position where a **non-zero element** should be placed |

### Rule

If `a[i] != 0`

```
swap(a[j], a[i])
j++
```

This ensures:

✔ Non-zero elements move to the **front**  
✔ Zeros automatically move to the **end**  
✔ Order of non-zero elements remains **unchanged**

---

## 📊 Visualization

### Initial

```
[0 0 3 0 0 5 0 0 7]
```

### Step 1 (found 3)

```
[3 0 0 0 0 5 0 0 7]
```

### Step 2 (found 5)

```
[3 5 0 0 0 0 0 0 7]
```

### Step 3 (found 7)

```
[3 5 7 0 0 0 0 0 0]
```

---

## 🧩 Pseudocode

```
function moveZerosToEnd(a[], n):

    j = 0

    for i from 0 to n-1:

        if a[i] != 0:
            swap(a[j], a[i])
            j = j + 1
```

---

## 💻 Code Implementation

### 🧩 C++

```cpp
#include <bits/stdc++.h>
using namespace std;

void moveZeros(int a[], int n) {

    int j = 0;

    for(int i = 0; i < n; i++) {

        if(a[i] != 0) {
            swap(a[j], a[i]);
            j++;
        }

    }

}
```

---

### 🐍 Python

```python
def move_zeros(arr):

    j = 0

    for i in range(len(arr)):

        if arr[i] != 0:
            arr[j], arr[i] = arr[i], arr[j]
            j += 1


arr = [0,0,3,0,0,5,0,0,7]

move_zeros(arr)

print(arr)
```

---

### ☕ Java

```java
class MoveZeros {

    static void moveZeros(int arr[], int n) {

        int j = 0;

        for(int i = 0; i < n; i++) {

            if(arr[i] != 0) {

                int temp = arr[j];
                arr[j] = arr[i];
                arr[i] = temp;
                j++;

            }

        }

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
✔ **No extra memory used**

---

## 🎯 Key Takeaways

- Uses **Two Pointer Technique**
- Maintains **order of non-zero elements**
- Runs in **O(n)** time
- Solves the problem **in-place**

---

⭐ **Created for learning by @techno_pathy**
