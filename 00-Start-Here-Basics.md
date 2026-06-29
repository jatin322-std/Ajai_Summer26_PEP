# 🧱 00 — Start Here: Absolute Basics

> If words like *array*, *loop*, or *time complexity* feel scary — this is the perfect place to begin. Read slowly. This is the floor everything else stands on.

---

## What is an Algorithm? (Explain Like I'm 5)

> 🍳 **Making tea is an algorithm:**
> 1. Boil water → 2. Add tea → 3. Add milk → 4. Add sugar → 5. Strain.
>
> An **algorithm** = a list of steps to solve a problem. DSA is just learning the *smartest* steps for computer problems. That's all it is.

---

## What is a Data Structure? (Explain Like I'm 5)

> 📦 **How you store things matters:**
> - Socks loose in a drawer = slow to find a pair.
> - Socks in labeled boxes = fast to find.
>
> A **data structure** = a way to organize data so the computer finds it quickly. An *array* is one such box. We learn them one at a time.

---

## What is an Array?

> 🥚 An array is **a row of boxes, numbered from 0** — like an egg tray.
> ```
> arr = [10, 20, 30]
>         ↑   ↑   ↑
> index:  0   1   2
> ```
> The box number is the **index**. **Arrays start at index 0, not 1.** Circle this — it confuses every beginner at first, and that's normal.

---

## What is Time Complexity / Big-O? (The thing everyone fears)

It sounds scary but answers ONE simple question:
> **"If the input gets bigger, does my code get slow?"**

> 🏃 **Story:** Finding a friend's name in a list.
> - 10 names → fast.
> - 1,00,000 names → if you check one-by-one, slow.
>
> Big-O measures **how the number of steps grows** as the input size `n` grows.

| Big-O | Name | Plain Meaning | Example |
|-------|------|---------------|---------|
| **O(1)** | Constant | Same speed always | Pick the 1st item |
| **O(log n)** | Logarithmic | Super fast even for huge data | Binary Search |
| **O(n)** | Linear | Grows fairly with size | Check each item once |
| **O(n²)** | Quadratic | Slow for big data | A loop inside a loop |

> 🧠 **The only rule for now:** Lower is better.
> `O(1)` < `O(log n)` < `O(n)` < `O(n²)`

---

## What is Space Complexity?

Same idea, but for **memory**: "Did I create extra boxes (arrays), or reuse what I had?"
- No extra storage → **O(1) space**.
- Made a new array of size `n` → **O(n) space**.

---

## ⭐ The 4-Question Ritual (Memorize This)

Every problem in class follows these 4 steps. If you learn nothing else, learn this:

> 1. **Brute force?** — The dumbest, slowest way that *works*. (Always start here. It's step 1, not an embarrassment.)
> 2. **Can we optimize?** — Any smarter trick? (Two pointers? Sorting? A counting array?)
> 3. **Time complexity?** — How fast?
> 4. **Space complexity?** — How much extra memory?

> ✅ **Beginner permission slip:** Reaching only step 1 (a working brute-force answer) is a real win. *A working answer beats no answer.* Optimization is a skill you grow into.

---

## Mini Glossary (Bookmark)

| Term | Plain Meaning |
|------|---------------|
| **Index** | Box number in an array. Starts at **0**. |
| **Loop / Iterate** | Repeat an action for each item. |
| **Pointer** | A variable holding a position, like `left` or `right`. |
| **Brute force** | Simplest correct solution, even if slow. |
| **Optimize** | Make it faster / use less memory. |
| **Dry run** | Tracing code by hand on paper, value by value. |
| **In-place** | Solving without a big extra array (O(1) space). |

---

## 🎯 Your First Tiny Wins (Warm-Up, Not Graded)

Try these on paper or in code. They build confidence:
1. Print numbers 1 to 10
2. Sum of first N numbers
3. Largest of three numbers
4. Even or odd
5. Reverse a string

> 👉 Once these feel easy, open `02-Arrays-Basics.md`. You're ready.
