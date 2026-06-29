# 📊 02 — Arrays: The Basics

> **The one idea:** An array is a row of numbered boxes, starting at index **0**. Master this and half of DSA opens up.

```
arr = [10, 20, 30, 40]
        0   1   2   3      ← these index numbers are everything
```

---

## Problem 1 — Find the Largest Element

**Idea (brute force):** Assume the first box is the biggest. Walk through the rest. If you see something bigger, update your answer.

<details>
<summary>☕ Java</summary>

```java
int max = arr[0];                       // assume first is biggest
for (int i = 1; i < arr.length; i++) {
    if (arr[i] > max) {                 // found someone bigger?
        max = arr[i];                   // update champion
    }
}
System.out.println(max);
```
</details>

<details>
<summary>🐍 Python</summary>

```python
max_val = arr[0]                        # assume first is biggest
for i in range(1, len(arr)):
    if arr[i] > max_val:                # found someone bigger?
        max_val = arr[i]                # update champion
print(max_val)
```
</details>

<details>
<summary>⚡ C++</summary>

```cpp
int max = arr[0];                       // assume first is biggest
for (int i = 1; i < n; i++) {
    if (arr[i] > max) {                 // found someone bigger?
        max = arr[i];                   // update champion
    }
}
cout << max;
```
</details>

> ⏱️ **Time:** O(n) — we check each box once · **Space:** O(1) — no extra boxes

---

## Problem 2 — Sum of All Elements

<details>
<summary>☕ Java</summary>

```java
int sum = 0;
for (int i = 0; i < arr.length; i++) {
    sum += arr[i];                      // keep adding
}
System.out.println(sum);
```
</details>

<details>
<summary>🐍 Python</summary>

```python
total = 0
for num in arr:
    total += num
print(total)
# Shortcut once you understand the long way: print(sum(arr))
```
</details>

<details>
<summary>⚡ C++</summary>

```cpp
int sum = 0;
for (int i = 0; i < n; i++) {
    sum += arr[i];
}
cout << sum;
```
</details>

> ⏱️ **Time:** O(n) · **Space:** O(1)

---

## Problem 3 — Linear Search

> 🔎 Check every box one by one until you find the target. Works on *any* array (sorted or not).
> ```
> Find 30 in [10, 20, 30, 40] → 10? no → 20? no → 30? YES (index 2)
> ```

<details>
<summary>☕ Java</summary>

```java
int linearSearch(int[] arr, int target) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) return i; // found at index i
    }
    return -1;                          // not found
}
```
</details>

<details>
<summary>🐍 Python</summary>

```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i                    # found at index i
    return -1                           # not found
```
</details>

<details>
<summary>⚡ C++</summary>

```cpp
int linearSearch(int arr[], int n, int target) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) return i; // found at index i
    }
    return -1;                          // not found
}
```
</details>

> ⏱️ **Time:** O(n) · **Space:** O(1)

---

## 🎯 Practice (Easy — You Can Do These)

Start with the first two. They're truly beginner-friendly.

| Problem | Where | Link |
|---------|-------|------|
| Largest element in array | GfG | https://www.geeksforgeeks.org/problems/largest-element-in-array4009/0 |
| Find smallest & second smallest | GfG | https://www.geeksforgeeks.org/problems/second-largest3735/1 |
| Linear Search | GfG | https://www.geeksforgeeks.org/problems/who-will-win-1587115621/1 |
| Find Numbers with Even Number of Digits | LeetCode | https://leetcode.com/problems/find-numbers-with-even-number-of-digits/ |
| Running Sum of 1d Array | LeetCode | https://leetcode.com/problems/running-sum-of-1d-array/ |

> 💡 **Tip:** Solving even ONE of these today is a real win. Don't aim for all five — aim for *understanding* one fully. I'm here if you get stuck on any line. 💪
