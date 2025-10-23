
A **homogeneous system** is a system of linear equations where **all constant terms are zero**.

> [!note] Why Is It Called “Homogeneous”?
> In mathematics, “homogeneous” originally meant **structurally uniform**—every term has the same type or degree.
>
> In a **homogeneous system of linear equations**, all constant terms are zero:
> $$
> A\vec{x} = \vec{0}
> $$
>
> Where:
>
> - $A$ is an $m \times n$ coefficient matrix
> - $\vec{x}$ is the vector of unknowns
> - $\vec{0}$ is the zero vector in $\mathbb{R}^m$
>
> This means:
>
> - Every equation is made **only of variables**
> - There are **no external offsets or constants**
>
> The system is **internally balanced**—it describes how variables relate to each other **without external influence**.

All homogenous systems have the **trivial solution** of all the variables equaling **zero**

If there exist other solutions to a **homogenous system**, then those solutions are **non-trivial**, and there must be **infinitely many** of them

> [!tip] Why infinitely many non-trivial solutions
> As all linear equations either has **no solution**, **one solution**, or **infinitely many**, since homogenous systems always has **at least the case of one solution**, if it has another non-trivial solution, it must have **infinitely many non-trivial solutions**

---

## 🧠 Properties of Homogeneous Systems

| Feature                     | Description |
|-----------------------------|-------------|
| Always consistent           | $x = 0$ is always a solution |
| May have infinite solutions | If there are free variables |
| Solution set forms a subspace | Closed under addition and scalar multiplication |
| Linked to null space        | All solutions lie in $\text{Null}(A)$ |

---

## 🧪 Example: Homogeneous System

Solve:

$$
\begin{aligned}
x + 2y - z &= 0 \\
3x - y + 4z &= 0 \\
2x + y + z &= 0
\end{aligned}
$$

Augmented matrix:

$$
\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\
3 & -1 & 4 & 0 \\
2 & 1 & 1 & 0
\end{array}\right]
$$

Reduce to RREF → extract parametric solution → describe null space.

---

## 🧠 Solution Types

| Case | Description | Interpretation |
|------|-------------|----------------|
| ✅ Only trivial solution | $x = 0$ | All variables are leading → no free variables |
| ♾️ Infinite solutions | Parametric form | At least one free variable → null space has dimension ≥ 1 |

---

### ✏️ Example: Infinite Solutions

Suppose RREF yields:

$$
\begin{bmatrix}
1 & 0 & 2 \\
0 & 1 & -1 \\
0 & 0 & 0
\end{bmatrix}
$$

Let $z = t$ (free variable), then:

- $x = -2t$
- $y = t$
- $z = t$

→ Solution set:
$$
\begin{bmatrix}
x \\
y \\
z
\end{bmatrix}
=
t
\begin{bmatrix}
-2 \\
1 \\
1
\end{bmatrix}
$$

→ Null space is 1-dimensional, spanned by $(-2,\ 1,\ 1)$

---

## 🧠 Semantic Audit: Homogeneous vs Non-Homogeneous

| Feature              | Homogeneous ($Ax = 0$) | Non-Homogeneous ($Ax = b$) |
|----------------------|------------------------|-----------------------------|
| Always consistent    | ✅ Yes                 | ❌ May be inconsistent       |
| Trivial solution     | ✅ Always              | ❌ Not guaranteed            |
| Infinite solutions   | ✅ Possible            | ✅ Possible                  |
| Solution set is subspace | ✅ Yes             | ❌ No (affine set)           |
| Linked to null space | ✅ Directly            | ❌ Only indirectly           |

---

## 🧵 Summary

| Concept         | Description |
|------------------|-------------|
| Homogeneous system | All constants = 0 |
| Always consistent | $x = 0$ always works |
| May have infinite solutions | Depends on pivot structure |
| Solution set is a subspace | Closed under addition and scaling |
| Null space of $A$ | Contains all solutions to $Ax = 0$ |
