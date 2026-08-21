# Homework 1: Titanic Data Questions

**Course:** ICC104 Machine Learning
**Unit:** I
**Session:** 2 of 7
**Format:** Individual assignment submitted through GitHub using a pull request

> **Prerequisite:** Complete **Lab 1: Titanic EDA** before beginning this homework. Lab 1 provides the WSL, Python environment, VS Code, and Git workflow required for this assignment. Do not repeat the environment setup for this homework.

## Objective

Answer the following 13 questions by writing pandas queries against the raw Titanic dataset.

This homework is not a reflection about Lab 1. You must write new queries to obtain each answer directly from the dataset. Each question has a specific answer that can be calculated using filtering, grouping, or aggregation. The last three questions also require a simple plot and a short interpretation of what the chart shows.

## Dataset setup

Load the dataset exactly as shown below, without applying any cleaning beforehand:

```python
import pandas as pd

url = "https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv"
df = pd.read_csv(url)
```

Unless a question explicitly states otherwise:

* Do not drop columns or rows.
* Do not replace missing values.
* Do not encode categorical variables.
* Answer each question using the dataset exactly as loaded.

You may perform your analysis in a Python script, Jupyter notebook, or Python REPL. However, your final submission must be a Word document.

## Required Word document format

Create a Word document named:

```text
U1_H1.docx
```

At the beginning of the document, include official Cetys Cover.

For each question, include the following parts:

1. **Question:** Copy the question or clearly identify its number.
2. **Answer:** Provide the numeric or short written answer.
3. **Pandas code:** Include the one or two lines of pandas code used to calculate the answer.
4. **For plot questions:** Insert the generated chart image and add a short interpretation of what the plot suggests.

Example:

**Question 0: How many passengers are included in the dataset?**

**Answer:** There are 891 passengers.

**Pandas code:**

```python
df.shape[0]
```

Paste code into Word as editable text, preferably using a monospaced font such as Consolas or Courier New. Do not submit screenshots of your code.


## Questions

### 1. Female survivors older than 50

How many female passengers survived who were older than 50?

### 2. Median fare of passengers who did not survive

What was the median fare paid by passengers who did **not** survive?

### 3. Third-class survival rate

What percentage of third-class passengers (`Pclass == 3`) survived?

Report the result as a percentage rounded to two decimal places.

### 4. Passengers by embarkation port

How many passengers embarked from each port (`S`, `C`, and `Q`)? How many rows have a missing `Embarked` value?

### 5. Average age of survivors by sex

What was the average age of male survivors? What was the average age of female survivors?

Which group was older on average?

### 6. Missing cabin and survival status

How many passengers with no recorded `Cabin` did **not** survive?

### 7. Traveling alone and survival

Compare the survival rate of:

* Passengers traveling completely alone: `SibSp == 0` and `Parch == 0`
* Passengers traveling with at least one family member aboard

Which group had the higher survival rate, and by how many percentage points?

### 8. Average fare by passenger class

What was the average fare paid by passengers in each passenger class (`Pclass` 1, 2, and 3)?

### 9. Passengers younger than 18

How many passengers younger than 18 years old were aboard? What was their survival rate?

### 10. Correlation between fare and passenger class

What is the correlation between `Fare` and `Pclass`?

State whether the correlation is positive or negative. In one sentence, explain whether the sign of the correlation matches your intuition and why.

### 11. Age distribution plot

Create a histogram of the `Age` column.

Then answer: what does the distribution suggest about the age of the passengers, and where is the largest concentration of values?

### 12. Survival by sex or passenger class

Create a bar chart showing the number of passengers who survived and did not survive by `Sex` or by `Pclass`.

Which group had the highest number of survivors, and what does the chart suggest about the relationship between the selected feature and survival?

### 13. Fare distribution by survival status

Create a box plot for `Fare` grouped by `Survived`.

What does the chart suggest about the typical fare paid by survivors versus non-survivors, and are there clear outliers?

## Submission instructions

Submit the Word document through the same GitHub workflow used in Lab 1.

Before beginning your work and again before submitting it, update your fork using the instructions in:

```text
Students/README.md
```