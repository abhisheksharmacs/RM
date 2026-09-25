# Training, Validation, and Testing in Machine Learning

When building a Machine Learning model, the available dataset is typically divided into  **three parts** :

1. **Training Set**
2. **Validation Set**
3. **Testing Set**

Each serves a different purpose in the model development process.

---

# 1. Training Set

The **training dataset** is used to teach the model.

During training, the algorithm:

* Reads the input features (X)
* Compares predicted output with actual output (Y)
* Adjusts its parameters (weights) to reduce error

### Purpose

* Learn patterns and relationships from data.
* Build the predictive model.

### Example

Suppose we have a dataset of student study hours and exam marks.

| Study Hours | Marks |
| ----------- | ----- |
| 2           | 40    |
| 4           | 55    |
| 6           | 70    |
| 8           | 85    |

The model learns that higher study hours generally lead to higher marks.

### Characteristics

* Largest portion of data.
* Used repeatedly during learning.
* Directly influences model parameters.

### Typical Size

* 60%–80% of total data.

---

# 2. Validation Set

The **validation dataset** is used while the model is being developed.

After training on the training set, the model is evaluated on validation data.

### Purpose

* Tune hyperparameters.
* Compare different models.
* Detect overfitting.

### Example

Suppose we are testing:

* Learning Rate = 0.01
* Learning Rate = 0.001

The validation set helps determine which learning rate produces better performance.

### Characteristics

* Not used to train the model.
* Used during model selection.
* Can be evaluated multiple times.

### Typical Size

* 10%–20% of total data.

---

# 3. Testing Set

The **testing dataset** is used only after the final model is selected.

It represents completely unseen data.

### Purpose

* Measure the final performance of the model.
* Estimate how well the model will perform in the real world.

### Example

After choosing the best model using validation data, we evaluate it on test data and obtain:

* Accuracy = 94%
* Precision = 92%
* Recall = 90%

These values represent the model's expected real-world performance.

### Characteristics

* Never used during training.
* Never used for tuning.
* Used only once at the end.

### Typical Size

* 10%–20% of total data.

---

# Data Splitting Example

Suppose we have  **10,000 records** .

| Dataset    | Percentage | Records |
| ---------- | ---------- | ------- |
| Training   | 70%        | 7,000   |
| Validation | 15%        | 1,500   |
| Testing    | 15%        | 1,500   |

---

# Workflow

```text
                Dataset
                    |
      --------------------------------
      |              |              |
 Training       Validation       Testing
    |                |              |
 Learn         Tune Parameters   Final Check
 Patterns      Select Model      Performance
    |
 Trained Model
```

---

# Why Do We Need All Three?

### Without Validation Set

The model may be repeatedly adjusted based on test results, causing information leakage.

### Without Test Set

We cannot know how the model performs on truly unseen data.

### Without Training Set

The model cannot learn anything.

---

# Overfitting Example

Imagine a student:

* Memorizes all previous question papers → Training Accuracy = 100%
* Performs poorly on new questions → Test Accuracy = 60%

This is called  **overfitting** .

The validation set helps identify overfitting before final testing.

---

# Comparison Table

| Aspect                          | Training Set   | Validation Set  | Testing Set            |
| ------------------------------- | -------------- | --------------- | ---------------------- |
| Used for Learning?              | Yes            | No              | No                     |
| Used for Hyperparameter Tuning? | No             | Yes             | No                     |
| Used for Final Evaluation?      | No             | No              | Yes                    |
| Seen During Training?           | Yes            | No              | No                     |
| Can Be Used Multiple Times?     | Yes            | Yes             | Ideally No             |
| Main Purpose                    | Learn Patterns | Model Selection | Performance Assessment |

---

# Real-Life Analogy

Consider preparing for an examination:

| ML Dataset     | Student Analogy                            |
| -------------- | ------------------------------------------ |
| Training Set   | Studying textbooks and notes               |
| Validation Set | Solving sample papers to check preparation |
| Testing Set    | Actual final examination                   |

The student learns from textbooks (training), improves preparation using sample papers (validation), and finally demonstrates performance in the real exam (testing).

### Key Takeaway

* **Training Set** → Learns patterns.
* **Validation Set** → Tunes and improves the model.
* **Testing Set** → Measures final real-world performance.
