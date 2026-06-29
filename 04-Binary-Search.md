# 🔍 04 — Binary Search

> **Explain Like I'm 5:** Finding a word in a dictionary. You don't read page 1, 2, 3... You open the **middle**, decide if your word is before or after, and throw away half the book instantly. Repeat. That's binary search — and it's *lightning fast*.

> ⚠️ **One golden rule:** Binary search only works on a **SORTED** array.

```
Find 7 in:  [1, 3, 5, 7, 9, 11]
             low      mid      high
mid = 5 → 7 > 5 → answer is on the RIGHT → throw away the left half → repeat
```

---

## The Core Code

<details>
<summary>☕ Java</summary>

```java
int binarySearch(int[] arr, int target) {
    int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;   // safe middle
        if (arr[mid] == target) return mid; // found it!
        else if (arr[mid] < target) low = mid + 1;  // go right
        else high = mid - 1;                // go left
    }
    return -1;                              // not found
}
```
</details>

<details>
<summary>🐍 Python</summary>

```python
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid                       # found it!
        elif arr[mid] < target:
            low = mid + 1                    # go right
        else:
            high = mid - 1                   # go left
    return -1                                # not found
```
</details>

<details>
<summary>⚡ C++</summary>

```cpp
int binarySearch(int arr[], int n, int target) {
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;   // safe middle
        if (arr[mid] == target) return mid; // found it!
        else if (arr[mid] < target) low = mid + 1;  // go right
        else high = mid - 1;                // go left
    }
    return -1;                              // not found
}
```
</details>

> ⏱️ **Time:** O(log n) — for 1,00,000 elements, only ~17 steps! · **Space:** O(1)

---

## 🧠 3 Beginner Traps (Read Carefully)

> 1. **The array MUST be sorted.** No exceptions.
> 2. Write `low + (high - low) / 2`, not `(low + high) / 2` — the second one can overflow on huge numbers.
> 3. Use `low <= high` (with the **=**). Forgetting the equals sign is the #1 beginner bug.

---

## Dry Run It (Do This On Paper!)

Find `7` in `[1, 3, 5, 7, 9]`:

| Step | low | high | mid | arr[mid] | Action |
|------|-----|------|-----|----------|--------|
| 1 | 0 | 4 | 2 | 5 | 7 > 5 → go right, low = 3 |
| 2 | 3 | 4 | 3 | 7 | 7 == 7 → **return 3** ✅ |

> Tracing it by hand like this is the fastest way to *truly* understand binary search. Do it once with paper and pen — it'll click.

---

## 🎯 Practice (Start Easy)

| Problem | Where | Link |
|---------|-------|------|
| Binary Search | LeetCode | https://leetcode.com/problems/binary-search/ |
| Search Insert Position | LeetCode | https://leetcode.com/problems/search-insert-position/ |
| First and Last Position of Element | LeetCode | https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/ |
| Floor in a Sorted Array | GfG | https://www.geeksforgeeks.org/problems/floor-in-a-sorted-array-1587115620/1 |
| Search in Rotated Sorted Array | LeetCode | https://leetcode.com/problems/search-in-rotated-sorted-array/ |

> 💡 **Do the first one ("Binary Search") until you can write it without looking.** That single problem is worth a whole day. Everything else here is just a small twist on it. I'm here for any doubt. 🙏
