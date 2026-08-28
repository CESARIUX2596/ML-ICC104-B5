# Lab1: Exploratory Data Analysis (Titanic)

**Course:** ICC104 Machine Learning · **Unit:** I · **Session:** 2 of 7
**Format:** Individual, Jupyter notebook, submitted via pull request
**Files:** this instructions file + `U1_L1_skeleton.ipynb` (the notebook you will complete. Copy it, don't edit it in place.)

---

## 0. Environment setup

You need a working `.venv` with `ipykernel`, `numpy`, `pandas`, and `matplotlib`, and VS Code connected to it. If you already have this working from Session 2, skip to Part 1.

**Windows and WSL:** Your repository is already in your Windows folder. Open that same folder from WSL for the Python setup and notebook work in this lab. Do not clone the repository again. Continue using your normal Windows tools for Git and pull requests.

### One-time: install WSL (skip if already installed)

1. Open **PowerShell as Administrator**: click Start, type `PowerShell`, right-click **Windows PowerShell**, choose **Run as administrator**.
2. Run:
   ```powershell
   wsl --install
   ```
   This enables WSL, installs WSL2, and installs **Ubuntu** (the default Linux distribution) in one step.
3. **Restart your computer** when prompted.
4. After restarting, an Ubuntu window should open by itself (or search "Ubuntu" in the Start menu and open it). The first launch takes a minute to finish installing.
5. It will ask you to create a **UNIX username and password**. This is separate from your Windows login. Pick anything, and remember it (you'll need the password for `sudo` commands below). The password won't show any characters as you type it. That's normal, just type it and press Enter.

**If `wsl --install` fails or does nothing:** your Windows version may be too old. Open **Settings → Windows Update**, install all pending updates, then try again. If it still fails, ask before spending more than 15 minutes stuck here alone.

Then, in the Ubuntu window:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y git python3 python3-venv python3-pip
```

`sudo` will ask for the UNIX password you just created. Typing it is normal even though nothing appears on screen. Verify with `git --version` and `python3 --version`. Both should print a version number with no errors.

Finally, on the **Windows** side, open VS Code, go to the Extensions panel, and install the **WSL** extension (publisher: Microsoft). You won't open VS Code manually. The steps below open it *from* the Ubuntu terminal, which connects it to WSL automatically.

### Every session: create/activate the venv and open VS Code

1. Open the **Ubuntu** app (Start menu).
2. Go to your project folder (adjust the path to your own - this is your Windows path with `C:` replaced by `/mnt/c`):
   ```bash
   cd /mnt/c/Users/<YourWindowsUsername>/<Path>/<To>/<Repositories>/<Diectory>/ML-ICC104-B5/Students/<YourStudentID>
   ```
3. Create the virtual environment (**only the first time**):
   ```bash
   python3 -m venv .venv
   ```
4. Activate it (**every time**, including this one):
   ```bash
   source .venv/bin/activate
   # prompt should now start with (.venv)
   ```
5. Install the packages this unit needs (**only the first time**):
   ```bash
   python -m pip install ipykernel numpy pandas matplotlib
   ```
6. Verify:
   ```bash
   python -c "import numpy, pandas, matplotlib; print('Environment ready.')"
   ```
7. Open the project in VS Code, connected through WSL:
   ```bash
   code .
   ```
   Confirm **WSL: Ubuntu** appears in the bottom-left corner of the VS Code window. Then `Ctrl+Shift+P` → **Python: Select Interpreter** → pick the one inside `./.venv`, and when you open your notebook, click **Select Kernel** (top-right) and pick the same `.venv`.

You'll do git operations (staging, committing, pushing, opening the PR) later from your regular Windows terminal or VS Code window. Do not do them from inside this WSL session.

---

## 1. Goal

This lab is the **bridge between loading raw data and solving Homework 1**. Instead of jumping straight to the final statistics questions, you first practice the exact workflow you need to understand, inspect, clean, and transform a dataset before asking questions of it.

By the end you will have a single Jupyter notebook that:

1. Loads and inspects the Titanic dataset.
2. Quantifies and visualizes data quality issues (missing values, duplicates).
3. Visualizes distributions and relationships between features and the target.
4. Cleans the data: handles missing values and duplicates, encodes categorical features, scales numeric features.
5. Builds a correlation matrix and identifies the strongest predictors of survival.
6. Saves the cleaned dataset to a file.

This is the same kind of data preparation work you will rely on in Homework 1: load the dataset, inspect it, understand data quality, and transform it into a structured form that supports analysis. The goal is fluency with the pandas/Matplotlib operations themselves, executed correctly, end to end.

### Documentation is part of the lab

This lab intentionally does **not** name the pandas or Matplotlib method for each task. Before completing each section, search the [pandas documentation](https://pandas.pydata.org/docs/) or the [Matplotlib documentation](https://matplotlib.org/stable/api/index.html), choose an appropriate operation, and read its parameters. In your notebook, add a short Markdown note for **three** choices you made. Each note must name the method/function you selected, link to its official documentation, and explain in one sentence why it fits the task.

---

## 2. Build the notebook

1. Copy `Assignments/Unit1/Lab1/U1_L1_skeleton.ipynb` to ```ML-ICC104-B5/Students/<YourStudentID>/Unit1/Lab1/U1_L1.ipynb` and do all your work in the copy. Use the folder-naming convention agreed in class.
2. The skeleton already has **Step 1 - Load & Inspect** filled in exactly as shown in class (same dataset URL). You don't need to retype it.
3. Every other section has `# TODO` code cells. Complete them in order. The section order matches the class walkthrough:

| Skeleton section | What to do | Your investigation |
|---|---|---|
| Step 1 - Load & Inspect | Already filled in | Use the raw Titanic CSV exactly as shown in class. |
| Step 2 - Data Quality | Report missing values by column and the number of repeated rows. | Find the DataFrame operations that answer each question. |
| Step 3 - Distributions | Plot at least 2 numeric columns and 1 categorical column. | Choose chart types that fit each kind of variable. |
| Step 4 - Relationships | Create at least 2 visualizations comparing a feature against `Survived`. | Choose a comparison that makes the survival pattern readable. |
| Step 5 - Cleaning | Treat missing values, remove repeated rows, encode categories, and scale numeric features. | Decide and briefly justify a treatment for missing values; consult the documentation for the transformations you choose. |
| Step 6 - Correlation & Top Predictors | Build and plot a correlation matrix; identify the top 3 non-target features most related to survival. | Determine which columns can participate in correlation and how to rank the results. |
| Step 7 - Save the cleaned dataset | Save the cleaned CSV for later work. | Look up the export options needed to prevent the index from becoming a data column. |


## 3. Submission

Do this part from your normal **Windows/Powershell** terminal or VS Code window (not the WSL/Ubuntu one from Part 0 unless you set up your git credential in WSL). Git works the same way you already learned in GitHub onboarding.

1. Save your notebook as `Students/<YourStudentID>/Unit1/Lab1/U1_L1.ipynb`, and confirm `Students/<YourStudentID>/Unit1/Lab1/titanic_clean.csv` is present too.
2. Follow the standard submission workflow from `students/README.md`:
   ```bash
   git status
   git add Students/<YourStudentID>/Laboratories/U1_L1.ipynb Students/<YourStudentID>/Laboratories/titanic_clean.csv
   git commit -m "Complete Lab 1: Titanic EDA"
   git push origin main
   ```
3. Open a pull request titled `"<Your Name> <YourStudentID> - Lab 1"`.
4. **Before you push, make sure your fork is up to date with the course repo.** See the "Keeping your fork up to date" section in `students/README.md` if you're not sure how (`git fetch upstream`, `git merge upstream/main`, `git push origin main`).

---
