
In **Linear Algebra**, a **vector is not restricted to being a column only**. It can be represented as either a **column vector** or a **row vector**.

### 1. Column Vector (Most Common in ML)

A column vector has a single column and multiple rows.

$$
\mathbf{x} =
\begin{bmatrix}
2 \\
4 \\
6
\end{bmatrix}
$$

* Size: \(3 \times 1\)
* Represents a point or feature values.
* Most machine learning textbooks and research papers use column vectors.

---

### 2. Row Vector

A row vector has a single row and multiple columns.

$$
\mathbf{x} =
\begin{bmatrix}
2 & 4 & 6
\end{bmatrix}
$$

* Size: \(1 \times 3\)

---

### Relationship Between Them

A row vector is simply the **transpose** of a column vector.

$$
\begin{bmatrix}
2\\
4\\
6
\end{bmatrix}^{T}
=
\begin{bmatrix}
2 & 4 & 6
\end{bmatrix}
$$

and

$$
\begin{bmatrix}
2 & 4 & 6
\end{bmatrix}^{T}
=
\begin{bmatrix}
2\\
4\\
6
\end{bmatrix}
$$

---

## Why Does Machine Learning Prefer Column Vectors?

Suppose a student has:

* Attendance = 80
* CGPA = 8.5
* Projects = 3

These features are often written as:

$$
x=
\begin{bmatrix}
80\\
8.5\\
3
\end{bmatrix}
$$

and weights as:

$$
w=
\begin{bmatrix}
0.2\\
0.5\\
1.0
\end{bmatrix}
$$

To compute a prediction, we use:

$$
w^T x
=
\begin{bmatrix}
0.2 & 0.5 & 1.0
\end{bmatrix}
\begin{bmatrix}
80\\
8.5\\
3
\end{bmatrix}
=
16+4.25+3
=
23.25
$$

This notation becomes very convenient when working with matrices and neural networks.

---

### Quick Rule

| Representation | Example                                 | Dimension    |
| -------------- | --------------------------------------- | ------------ |
| Column Vector  | \(\begin{bmatrix}1\\2\\3\end{bmatrix}\) | \(3\times1\) |
| Row Vector     | \(\begin{bmatrix}1&2&3\end{bmatrix}\)   | \(1\times3\) |

So, **a vector can be either a row vector or a column vector.** However, in **machine learning, data samples and parameter vectors are usually represented as column vectors by convention.**
