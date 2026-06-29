# 🔤 05 — Strings

> 🪄 **The one mantra for all of strings:**
> **"A String is just an array of characters."**
> Everything you learned about arrays — two pointers, counting — works here. You already know strings. You just don't know it yet.

---

## The 2 Weapons That Solve Almost Every String Problem

1. **Two pointers** → reverse, palindrome
2. **A frequency/count array `int[26]`** → anagram, unique character

---

## The Magic `c - 'a'` Trick (Spend Real Time Here)

> 🔑 Letters have secret numbers (ASCII): `'a'` = 97, `'b'` = 98, ... `'z'` = 122.
> So:
> - `'a' - 'a'` = 0
> - `'b' - 'a'` = 1
> - `'z' - 'a'` = 25
>
> `c - 'a'` turns any lowercase letter into a number **0–25**. That lets a 26-box array act as a "letter counter." **Half of string problems depend on this one line.**

---

## Problem 1 — Check Palindrome (two pointers)

> A palindrome reads the same both ways: `madam`, `racecar`.

<details>
<summary>☕ Java</summary>

```java
boolean isPalindrome(String s) {
    int left = 0, right = s.length() - 1;
    while (left < right) {
        if (s.charAt(left) != s.charAt(right)) return false;
        left++;
        right--;
    }
    return true;
}
```
</details>

<details>
<summary>🐍 Python</summary>

```python
def is_palindrome(s):
    left, right = 0, len(s) - 1
    while left < right:
        if s[left] != s[right]:
            return False
        left += 1
        right -= 1
    return True
    # Shortcut (learn the long way first): return s == s[::-1]
```
</details>

<details>
<summary>⚡ C++</summary>

```cpp
bool isPalindrome(string s) {
    int left = 0, right = s.size() - 1;
    while (left < right) {
        if (s[left] != s[right]) return false;
        left++;
        right--;
    }
    return true;
}
```
</details>

---

## Problem 2 — Check Anagram (frequency array)

> Two words are anagrams if they use the **same letters**: `listen` & `silent`.
> **Trick:** Count letters in word A, subtract for word B. If all counts end at 0 → they match.

<details>
<summary>☕ Java</summary>

```java
boolean isAnagram(String a, String b) {
    if (a.length() != b.length()) return false;
    int[] count = new int[26];                  // 26 boxes, one per letter
    for (int i = 0; i < a.length(); i++) {
        count[a.charAt(i) - 'a']++;             // add for word a
        count[b.charAt(i) - 'a']--;             // subtract for word b
    }
    for (int c : count) if (c != 0) return false;
    return true;
}
```
</details>

<details>
<summary>🐍 Python</summary>

```python
def is_anagram(a, b):
    if len(a) != len(b):
        return False
    count = [0] * 26                            # 26 boxes, one per letter
    for i in range(len(a)):
        count[ord(a[i]) - ord('a')] += 1        # add for word a
        count[ord(b[i]) - ord('a')] -= 1        # subtract for word b
    return all(c == 0 for c in count)
    # Shortcut: from collections import Counter; return Counter(a) == Counter(b)
```
</details>

<details>
<summary>⚡ C++</summary>

```cpp
bool isAnagram(string a, string b) {
    if (a.size() != b.size()) return false;
    int count[26] = {0};                        // 26 boxes, one per letter
    for (int i = 0; i < a.size(); i++) {
        count[a[i] - 'a']++;                    // add for word a
        count[b[i] - 'a']--;                    // subtract for word b
    }
    for (int c : count) if (c != 0) return false;
    return true;
}
```
</details>

---

## ⚠️ Java Gotcha (Drill Once)

> In Java, `String` is **immutable** — it can't be changed after creation.
> Doing `s = s + c` inside a loop is secretly **O(n²)** (slow!).
> Use a **`char[]`** or **`StringBuilder`** instead when building strings in a loop.

---

## 🎯 Practice (Easy First)

| Problem | Where | Link |
|---------|-------|------|
| Valid Palindrome | LeetCode | https://leetcode.com/problems/valid-palindrome/ |
| Valid Anagram | LeetCode | https://leetcode.com/problems/valid-anagram/ |
| First Unique Character in a String | LeetCode | https://leetcode.com/problems/first-unique-character-in-a-string/ |
| Reverse String | LeetCode | https://leetcode.com/problems/reverse-string/ |
| Reverse Words in a String | LeetCode | https://leetcode.com/problems/reverse-words-in-a-string/ |

> 💡 **Order to attack:** Reverse String → Valid Palindrome → Valid Anagram. Each one reuses the *exact* two weapons above. Notice the pattern repeating — that's the moment strings stop feeling scary. 🌟
