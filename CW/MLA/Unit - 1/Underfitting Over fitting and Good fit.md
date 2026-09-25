# Underfitting and Overfitting Through a Simple Example

Imagine you are a teacher trying to predict a student's **final exam marks** based on the  **number of hours studied per week** .

### Training Data

| Study Hours | Marks |
| ----------- | ----- |
| 2           | 35    |
| 4           | 45    |
| 6           | 60    |
| 8           | 75    |
| 10          | 85    |

The trend is clear:

> More study hours → Higher marks

---

# Case 1: Underfitting

Suppose we build a very simple model:

```text
Marks = 50
```

No matter how many hours a student studies, the model always predicts 50.

| Study Hours | Actual Marks | Predicted |
| ----------- | ------------ | --------- |
| 2           | 35           | 50        |
| 4           | 45           | 50        |
| 6           | 60           | 50        |
| 8           | 75           | 50        |
| 10          | 85           | 50        |

### Problem

The model fails to learn the relationship between study hours and marks.

It is too simple.

### Result

* High training error
* High testing error
* High Bias

➡️ **Underfitting**

### Real-Life Meaning

It's like a teacher saying:

> "All students score around 50 marks."

without considering how much they studied.

---

# Case 2: Overfitting

Now suppose we create a very complex model.

The model memorizes every training record exactly:

```text
2 hours  → 35 marks
4 hours  → 45 marks
6 hours  → 60 marks
8 hours  → 75 marks
10 hours → 85 marks
```

It even learns accidental variations (noise).

Now a new student studies  **7 hours** .

A reasonable prediction would be around  **67–70 marks** .

But the overfitted model may behave strangely because it is trying to fit every training point perfectly.

### Result

* Almost zero training error
* Poor performance on new data
* High Variance

➡️ **Overfitting**

### Real-Life Meaning

It's like a teacher memorizing:

> "Rahul got 35, Priya got 45, Amit got 60..."

but not understanding the actual pattern that more study generally leads to better marks.

---

# Case 3: Good Fit

A balanced model learns:

```text
More Study Hours → More Marks
```

It doesn't memorize every student.

Instead, it learns the overall trend.

For a new student studying 7 hours:

```text
Predicted Marks ≈ 68–70
```

### Result

* Low training error
* Low testing error
* Good generalization

➡️ **Ideal Model**

---

# Another Easy Example: Age vs Height

Suppose we have data for children:

| Age | Height (cm) |
| --- | ----------- |
| 5   | 105         |
| 6   | 112         |
| 7   | 118         |
| 8   | 125         |
| 9   | 130         |

### Underfitting

Predict:

```text
Height = 120 cm
```

for every child.

Clearly wrong.

### Overfitting

Create a complicated curve passing through every point exactly.

It may predict absurd heights for age 7.5 or 10.

### Good Fit

Learn:

```text
As age increases, height generally increases.
```

This works well for unseen children too.

---

# Quick Summary

Imagine fitting a curve through data points:

```text
Underfitting         Good Fit          Overfitting

   /                   ~~~              /\/\/\/\
  /                   /   \            /        \
 /                   /     \          /\/\/\/\/\/\
```

* **Underfitting:** Model is too simple and misses the pattern.
* **Overfitting:** Model is too complex and memorizes the data.
* **Good Fit:** Model captures the actual trend and works well on new data.

### Exam Point of View

**Underfitting:** Learning too little from the data.
**Overfitting:** Learning the data and its noise.
**Good Fit:** Learning the true pattern while ignoring noise.
