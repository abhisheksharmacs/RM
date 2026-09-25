# Linear Algebra for Machine Learning

Linear Algebra is the mathematical foundation of Machine Learning. Almost every ML algorithm—from Linear Regression to Deep Neural Networks—uses vectors, matrices, and matrix operations to represent, process, and learn from data.

---

# 1. Why Linear Algebra is Important in Machine Learning?

Suppose you have a dataset of students:

| Student | Age | Study Hours | Attendance |
| ------- | --- | ----------- | ---------- |
| A       | 18  | 5           | 90         |
| B       | 19  | 6           | 85         |
| C       | 20  | 7           | 95         |

Instead of storing data separately, ML represents it as a **matrix**:

$$
X=
\begin{bmatrix}
18 & 5 & 90\\
19 & 6 & 85\\
20 & 7 & 95
\end{bmatrix}
$$

This matrix becomes the input to machine learning algorithms.

---

# 2. Scalars, Vectors, Matrices, and Tensors

## A. Scalar

A single number.

Examples:

$$
5,\quad -3,\quad 0.75
$$

In ML:

* Learning Rate = 0.01
* Accuracy = 95%

---

## B. Vector

An ordered list of numbers.

$$
v=
\begin{bmatrix}
2\\
4\\
6
\end{bmatrix}
$$

Represents:

* Feature values
* Weights
* Predictions

Example:

Student marks in 3 subjects:

$$
v=
\begin{bmatrix}
80\\
70\\
90
\end{bmatrix}
$$

---

## C. Matrix

Collection of vectors arranged in rows and columns.

$$
A=
\begin{bmatrix}
1&2\\
3&4
\end{bmatrix}
$$

Applications:

* Dataset representation
* Image processing
* Neural network weights

---

## D. Tensor

Generalization of matrices to multiple dimensions.

Examples:

* Scalar → 0D Tensor
* Vector → 1D Tensor
* Matrix → 2D Tensor
* RGB Image → 3D Tensor

Deep Learning frameworks like TensorFlow and PyTorch use tensors.

---

# 3. Matrix Operations

---

## A. Matrix Addition

Possible only when dimensions are same.

$$
A=
\begin{bmatrix}
1&2\\
3&4
\end{bmatrix}
$$

$$
B=
\begin{bmatrix}
5&6\\
7&8
\end{bmatrix}
$$

$$
A+B=
\begin{bmatrix}
6&8\\
10&12
\end{bmatrix}
$$

---

## B. Scalar Multiplication

Multiply every element by a constant.

$$
2A=
\begin{bmatrix}
2&4\\
6&8
\end{bmatrix}
$$

---

## C. Matrix Multiplication

One of the most important operations in ML.

$$
A=
\begin{bmatrix}
1&2\\
3&4
\end{bmatrix}
$$

$$
B=
\begin{bmatrix}
5&6\\
7&8
\end{bmatrix}
$$

$$
AB=
\begin{bmatrix}
19&22\\
43&50
\end{bmatrix}
$$

### Why Important?

Neural networks compute:

$$
Z = WX + b
$$

where

* W = weight matrix
* X = input vector
* b = bias

---

# 4. Transpose of a Matrix

Rows become columns.

$$
A=
\begin{bmatrix}
1&2&3\\
4&5&6
\end{bmatrix}
$$

$$
A^T=
\begin{bmatrix}
1&4\\
2&5\\
3&6
\end{bmatrix}
$$

Applications:

* Linear Regression
* Covariance Matrix
* PCA

---

# 5. Dot Product

The most frequently used vector operation.

$$
a=
\begin{bmatrix}
1\\
2\\
3
\end{bmatrix}
$$

$$
b=
\begin{bmatrix}
4\\
5\\
6
\end{bmatrix}
$$

$$
a\cdot b
=
1(4)+2(5)+3(6)
=
32
$$

---

## Geometric Interpretation

$$
a\cdot b
=
|a||b|\cos\theta
$$

where

$$
\theta
$$

is the angle between vectors.

---

### ML Use Case

Prediction in Linear Regression:

$$
y = w^Tx + b
$$

where:

$$
w=
\begin{bmatrix}
2\\
3
\end{bmatrix}
$$

$$
x=
\begin{bmatrix}
5\\
4
\end{bmatrix}
$$

Prediction:

$$
y=(2)(5)+(3)(4)=22
$$

---

# 6. Vector Norms

Norm measures vector length.

---

## L1 Norm

$$
||x||_1
=
\sum |x_i|
$$

Example:

$$
x=
\begin{bmatrix}
2\\
-3\\
4
\end{bmatrix}
$$

$$
||x||_1
=
2+3+4
=
9
$$

Used in:

* Lasso Regression
* Feature Selection

---

## L2 Norm

$$
||x||_2
=
\sqrt{\sum x_i^2}
$$

$$
||x||_2
=
\sqrt{2^2+(-3)^2+4^2}
=
\sqrt{29}
$$

Used in:

* Ridge Regression
* Distance Calculations

---

# 7. Distance Measures

---

## Euclidean Distance

$$
d=
\sqrt{\sum(x_i-y_i)^2}
$$

Example:

$$
P=(1,2)
$$

$$
Q=(4,6)
$$

$$
d=
\sqrt{(4-1)^2+(6-2)^2}
=
5
$$

Used in:

* KNN
* Clustering

---

## Manhattan Distance

$$
d=
\sum |x_i-y_i|
$$

Example:

$$
d=|4-1|+|6-2|
=
7
$$

Used in:

* Route optimization
* Sparse data

---

# 8. Linear Independence

Vectors are linearly independent if one cannot be expressed as a combination of others.

Example:

$$
v_1=
\begin{bmatrix}
1\\
0
\end{bmatrix}
$$

$$
v_2=
\begin{bmatrix}
0\\
1
\end{bmatrix}
$$

Independent.

---

## Why Important?

Highly correlated features create redundancy.

Example:

* Salary
* Annual Salary

Both carry same information.

Machine learning models perform better with independent features.

---

# 9. Rank of a Matrix

Rank = Number of independent rows or columns.

Example:

$$
A=
\begin{bmatrix}
1&2\\
2&4
\end{bmatrix}
$$

Second row is multiple of first row.

Rank = 1

---

### ML Importance

Low rank indicates:

* Redundant features
* Multicollinearity

Used in:

* PCA
* Feature reduction

---

# 10. Eigenvalues and Eigenvectors

One of the most important concepts in ML.

For matrix A:

$$
Av=\lambda v
$$

where

* \(v\) = Eigenvector
* \(\lambda\) = Eigenvalue

---

## Intuition

When matrix transforms vector:

* Direction remains same
* Length changes

---

### Example

$$
A=
\begin{bmatrix}
2&0\\
0&3
\end{bmatrix}
$$

For

$$
v=
\begin{bmatrix}
1\\
0
\end{bmatrix}
$$

$$
Av=
\begin{bmatrix}
2\\
0
\end{bmatrix}
=
2v
$$

Eigenvalue = 2

---

## ML Applications

### PCA

Principal Component Analysis finds:

* Maximum variance directions
* Data compression

Using eigenvalues and eigenvectors of covariance matrix.

---

# 11. Singular Value Decomposition (SVD)

Any matrix can be decomposed as:

$$
A=U\Sigma V^T
$$

Applications:

* Recommendation Systems
* Image Compression
* NLP
* Dimensionality Reduction

---

# 12. Linear Algebra in Common ML Algorithms

| Algorithm              | Linear Algebra Used            |
| ---------------------- | ------------------------------ |
| Linear Regression      | Matrix multiplication, inverse |
| Logistic Regression    | Vectors, dot product           |
| KNN                    | Distance measures              |
| SVM                    | Dot product                    |
| PCA                    | Eigenvalues/Eigenvectors       |
| Neural Networks        | Matrix multiplication          |
| Deep Learning          | Tensors                        |
| Recommendation Systems | SVD                            |

---

# Numerical Problems

## Problem 1: Dot Product

Given:

$$
a=
\begin{bmatrix}
2\\
3
\end{bmatrix}
$$

$$
b=
\begin{bmatrix}
4\\
5
\end{bmatrix}
$$

Find \(a \cdot b\).

### Solution

$$
(2)(4)+(3)(5)
$$

$$
=8+15
$$

$$
=23
$$

---

## Problem 2: Matrix Addition

$$
A=
\begin{bmatrix}
1&2\\
3&4
\end{bmatrix}
$$

$$
B=
\begin{bmatrix}
5&6\\
7&8
\end{bmatrix}
$$

Find \(A+B\).

### Solution

$$
\begin{bmatrix}
6&8\\
10&12
\end{bmatrix}
$$

---

## Problem 3: Matrix Multiplication

$$
A=
\begin{bmatrix}
1&2\\
3&4
\end{bmatrix}
$$

$$
B=
\begin{bmatrix}
2&0\\
1&5
\end{bmatrix}
$$

Find \(AB\).

### Solution

$$
AB=
\begin{bmatrix}
(1)(2)+(2)(1) & (1)(0)+(2)(5)\\
(3)(2)+(4)(1) & (3)(0)+(4)(5)
\end{bmatrix}
$$

$$
=
\begin{bmatrix}
4&10\\
10&20
\end{bmatrix}
$$

---

## Problem 4: Euclidean Distance

Points:

$$
(2,3)
$$

and

$$
(6,6)
$$

### Solution

$$
d=
\sqrt{(6-2)^2+(6-3)^2}
$$

$$
=
\sqrt{16+9}
$$

$$
=
5
$$

---

## Problem 5: L2 Norm

$$
x=
\begin{bmatrix}
3\\
4
\end{bmatrix}
$$

### Solution

$$
||x||_2
=
\sqrt{3^2+4^2}
$$

$$
=
5
$$

---

# Quick Exam Revision Sheet

### Must Know Definitions

1. Scalar
2. Vector
3. Matrix
4. Tensor
5. Dot Product
6. Matrix Multiplication
7. Transpose
8. Norm
9. Rank
10. Eigenvalue
11. Eigenvector
12. SVD

### Most Important ML Applications

* Dataset Representation → Matrices
* Linear Regression → Matrix Algebra
* KNN → Distance Measures
* PCA → Eigenvalues & Eigenvectors
* Deep Learning → Matrix Multiplication & Tensors
* Recommendation Systems → SVD

### Frequently Asked M.Tech Exam Questions

1. Explain vectors, matrices, and tensors with ML examples.
2. Derive dot product and discuss its role in linear regression.
3. Explain matrix multiplication in neural networks.
4. What are eigenvalues and eigenvectors? Explain PCA.
5. Explain rank and linear independence with examples.
6. Compare L1 and L2 norms.
7. Explain SVD and its applications in ML.
8. Solve numerical problems on matrix operations, norms, and distances.

For an **M.Tech Machine Learning exam**, the highest-priority topics are **matrix multiplication, dot product, vector norms, linear independence, rank, eigenvalues/eigenvectors, PCA, and SVD**, since they directly connect linear algebra to ML algorithms.
