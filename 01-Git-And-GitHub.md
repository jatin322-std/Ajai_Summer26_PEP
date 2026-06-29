# ⚙️ 01 — Git & GitHub

> **Goal:** Save your code forever, and build a daily habit recruiters will love.

---

## Why GitHub? (Story)

> 💾 Imagine coding for 6 months. Your laptop crashes. **Everything gone.**
> GitHub is a free cloud locker for your code. We upload daily — it builds discipline *and* a portfolio recruiters can actually see.

---

## Setup Checklist

- [ ] Install **Git** → check with `git --version`
- [ ] Make a free **GitHub account**
- [ ] Pick your language tool: **Java JDK** / **Python** / **g++ (C++)**

Verify in the terminal:
```bash
java --version     # Java users
python --version   # Python users
g++ --version      # C++ users
git --version      # everyone
```
If a version number prints — you're good. ✅

---

## The Only 5 Git Commands You Need (For Now)

```bash
git init                       # start tracking a folder (do once)
git status                     # see what changed
git add .                      # stage all changes
git commit -m "Arrays done"    # save a snapshot with a message
git push                       # upload to GitHub
```

> 🧠 **Mental model:**
> `add` = put files in a box → `commit` = seal & label the box → `push` = ship it to GitHub.

---

## First-Time Setup (one time only)

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## Connecting Your Folder To GitHub (one time per repo)

```bash
git init
git add .
git commit -m "First commit"
git branch -M main
git remote add origin https://github.com/yourname/your-repo.git
git push -u origin main
```

After that first push, your daily routine is just:
```bash
git add .
git commit -m "Today's work"
git push
```

---

## 📁 Suggested Folder Structure

```
DSA-Preparation/
├── Arrays/
├── Two-Pointers/
├── Binary-Search/
├── Strings/
└── Sorting/
```

> 🎯 **Habit goal:** Push something every single day. Even one solved problem. Small daily wins compound into a strong portfolio by placement season.
