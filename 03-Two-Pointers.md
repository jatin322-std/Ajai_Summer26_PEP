# 🤝 03 — Two Pointers

> **Explain Like I'm 5:** Imagine two fingers — one on the **left** end, one on the **right** end of the array. They walk toward each other and meet in the middle. That's the two-pointer technique. It's one of the most powerful beginner tricks in all of DSA.

```
[ 1, 2, 3, 4, 5 ]
  ↑           ↑
 left       right     → they move toward each other
```

---

## Use 1 — Reverse an Array (in place)

**Idea:** Swap the two ends, then step both pointers inward. Repeat until they meet.

<details>
<summary>☕ Java</summary>

```java
int left = 0, right = arr.length - 1;
while (left < right) {
    int temp = arr[left];               // swap the two ends
    arr[left] = arr[right];
    arr[right] = temp;
    left++;                             // step inward
    right--;
}
```
</details>

<details>
<summary>🐍 Python</summary>

```python
left, right = 0, len(arr) - 1
while left < right:
    arr[left], arr[right] = arr[right], arr[left]   # swap (Python makes this easy!)
    left += 1
    right -= 1
```
</details>

<details>
<summary>⚡ C++</summary>

```cpp
int left = 0, right = n - 1;
while (left < right) {
    swap(arr[left], arr[right]);        // built-in swap
    left++;
    right--;
}
```
</details>

> ⏱️ **Time:** O(n) · **Space:** O(1). We touch each element once and use no extra array.

---

## Use 2 — Pair With Target Sum (on a SORTED array)

> **Problem:** Given a *sorted* array, is there a pair that adds up to a target?
> **Trick:** If the sum is too small, move `left` right (to get bigger). If too big, move `right` left (to get smaller).

<details>
<summary>☕ Java</summary>

```java
int left = 0, right = arr.length - 1;
while (left < right) {
    int sum = arr[left] + arr[right];
    if (sum == target) return true;     // found the pair!
    else if (sum < target) left++;      // need a bigger sum
    else right--;                       // need a smaller sum
}
return false;
```
</details>

<details>
<summary>🐍 Python</summary>

```python
left, right = 0, len(arr) - 1
while left < right:
    s = arr[left] + arr[right]
    if s == target:
        return True                     # found the pair!
    elif s < target:
        left += 1                       # need a bigger sum
    else:
        right -= 1                      # need a smaller sum
return False
```
</details>

<details>
<summary>⚡ C++</summary>

```cpp
int left = 0, right = n - 1;
while (left < right) {
    int sum = arr[left] + arr[right];
    if (sum == target) return true;     // found the pair!
    else if (sum < target) left++;      // need a bigger sum
    else right--;                       // need a smaller sum
}
return false;
```
</details>

> ⏱️ **Time:** O(n) · **Space:** O(1). Compare this to checking every pair, which is O(n²) — the two-pointer trick is the optimization.

---

## 🎯 Practice (Easy → Easy-Medium)

| Problem | Where | Link |
|---------|-------|------|
| Reverse String (array of chars) | LeetCode | https://leetcode.com/problems/reverse-string/ |
| Two Sum II — Input Array Is Sorted | LeetCode | https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/ |
| Squares of a Sorted Array | LeetCode | https://leetcode.com/problems/squares-of-a-sorted-array/ |
| Move Zeroes | LeetCode | https://leetcode.com/problems/move-zeroes/ |
| Remove Duplicates from Sorted Array | LeetCode | https://leetcode.com/problems/remove-duplicates-from-sorted-array/ |

> 💡 **Start with "Reverse String"** — it's the gentlest two-pointer problem on LeetCode. Once it clicks, the rest follow the same shape. You've got this. 🙌
