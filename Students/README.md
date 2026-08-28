# Student Submission Guide

Welcome! This page is everything you need to submit work in this course. Read it once now, then keep it bookmarked — you'll follow the same steps for every homework, lab, and project all semester.

Full explanations of every concept mentioned here (fork, clone, commit, pull request...) are in `course-content/unit-1-introduction/presentations/ML_U1_GitHub_Guide.md` and were covered in class. This page is the **quick reference**.

---

## One-time setup

1. **Create a GitHub account** if you don't have one: <https://github.com/join>
2. **Install Git** on your computer and confirm it works:
   ```bash
   git --version
   ```
3. **Fork the course repository** — open it on GitHub and click **Fork** (top-right).
4. **Clone your fork** to your computer:
   ```bash
   git clone https://github.com/YOUR-USERNAME/ML-ICC104-B5.git
   cd ML-ICC104-B5
   ```
5. **Tell Git who you are** (once per computer):
   ```bash
   git config --global user.name "Your Full Name"
   git config --global user.email "you@example.com"
   ```
6. **Link the original course repo** so you can pull updates:
   ```bash
   git remote add upstream https://github.com/CESARIUX2596/ML-ICC104-B5.git
   ```

---

## Find your directory

Your workspace is `Students/<YourStudentID>/`. The instructor creates this folder for you — if it doesn't exist yet, ask before starting work.

```
ML-ICC104-B5/
└── Students/
    └── your-student-id/        ← everything you submit goes here, and only here
```

**Do not create, edit, or delete files outside your own directory.** Touching another student's folder or shared course files will get your pull request rejected and may raise an academic-integrity concern.

---

## The submission workflow (every assignment)

```bash
# 1. Start from the latest version
git pull origin master

# 2. Do your work inside Students/your-student-id/

# 3. Check what changed
git status

# 4. Stage your files
git add Students/your-student-id/homeworkN.ipynb

# 5. Commit with a clear message
git commit -m "Complete homework N: <short description>"

# 6. Push to your fork
git push origin master
```

Then open a **pull request**:

1. Go to your fork on GitHub.
2. Click **Compare & pull request** (or **Pull requests → New pull request**).
3. Confirm: base = course repo `master` ← compare = your fork `master`.
4. Title it clearly, e.g. `"Fulanito Perez — Homework 2"`.
5. Click **Create pull request**.

The instructor reviews and merges it. If they leave comments, fix the files locally and repeat steps 3–6, **don't open a new PR**, your existing one updates automatically.

---

## Keeping your fork up to date

> Important: Always check for new updates before you start work and before you commit. If the course repo changes while you are working on your files, you may create merge conflicts that are easy to avoid by syncing first.

Do this **before starting new work**, whenever the instructor adds material:

```bash
git fetch upstream
git merge upstream/master
git push origin master
```

Need a quick reference while working? Use the Pandas cheat sheet for DataFrame commands: <https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf>

Optional Git quick reference: <https://education.github.com/git-cheat-sheet-education.pdf>

---

## What never gets committed

Your `.gitignore` (already in the repo) blocks most of these automatically, but double-check before every commit:

- Virtual environments (`.venv/`, `venv/`, `__pycache__/`)
- Jupyter checkpoints (`.ipynb_checkpoints/`)
- Secrets — `.env` files, API keys, passwords, credentials of any kind
- Large raw datasets — use a download script or link instead of committing multi-MB CSVs
- OS junk files (`.DS_Store`, `Thumbs.db`)

If you're ever unsure whether a file should be committed, run `git status` and look before you `git add`.

---

## First assignment: your Git/GitHub practice PR

Before Session 2, complete the full workflow once:

1. Inside `Students/your-student-id/`, create a file named `intro.md`.
2. Include:
   - Your name and program/major
   - Your programming experience
   - Your experience with statistics or data analysis
   - Whether you've used Machine Learning before
   - One thing you'd like to learn in this course
   - A short reflection (2–4 sentences) on what excites or worries you about ML
3. Commit, push, and open a pull request titled with your name.

This is graded on completing the workflow correctly, not on the content of your reflection.

---

## Quick troubleshooting

| Problem | Fix |
|---|---|
| `Permission denied` when pushing | You're pushing to `upstream` instead of `origin`. Push to `origin` — that's your fork. |
| `git push` rejected, says "fetch first" | Someone (or you, elsewhere) added commits you don't have. Run `git pull origin master` first. |
| Not sure what changed | `git status` — always safe to run, shows staged/unstaged files. |
| Committed something you shouldn't have | Ask the instructor before force-pushing or rewriting history — don't try to fix it alone. |

Stuck on anything else? Ask in class, or via the contact method listed in the course syllabus.
