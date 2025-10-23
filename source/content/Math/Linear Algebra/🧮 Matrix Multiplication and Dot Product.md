
Fundamentally **matrices** are **sets of numbers grouped together in organised ways** where the axis represent the different factors we are grouping them by.

> [!note] Parallel in Computer Science
> In computer science, matrices resemble **arrays**—but in linear algebra, they are more strict with **preserving orientation**

---

## 🔧 Preserving Linearity in Arithmetic

Operations between numbers must **maintain the current level of abstraction** in order to remain **linear**.

- This includes **addition and subtraction**, which operate directly on values without changing their structural role:

$$
a + b = c \quad\text{and}\quad a - b = d
$$

- When we have **repeated addition/subtraction** between numbers, we simply **shorten its representation** and call it **multiplication**:

$$
a + a + a + \dots + a = a \cdot n
$$

> [!tip] Generalisation of Multiplication
> Even in its **generalized form**, multiplication remains semantically additive:
>
> - For **rational scalars**, multiplication represents repeated addition of fractional parts.
> - For **irrational scalars**, multiplication is defined via **limit-based additive constructions**—approximating the scalar through sequences of rational additions.
> - In analysis, multiplication by a real number corresponds to **continuous additive accumulation**, often formalized through **integration** or **area under a curve**.

---

## 🚫 Why Division Is Not Linear

**Scalar multiplication** applies a process to reach a result.

$$a \cdot n$$

> [!note] Abstraction-Preserving
> It stays within the abstraction as the **original number** is still **the one being dealt with**

**Division** finds **how many times the process was applied** to get to the result

$$\dfrac{c}{a} = n$$

> [!note] Abstraction Shift
> Division **shifts the abstraction** away from the original numbers
>
> Therefore, it is **not a linear operation**

---

## 🧮 Linearity in Matrix Operations

In linear algebra, we group numbers together in **organised rows and columns** called **matrices**.

> [!tip] Linearity of Matrices
> **Maintaining linearity in matrices** requires
>
> - Maintaining the **position of each number relative to one another**
> - Each number must also maintain their **relative magnitude to one another**
>
> Otherwise, matrices cannot be meaningfully be said to be the same after transformation

**Unique orientation of numbers** is what make matrices unique

---

### ➕ Matrix Addition

$$ A \pm B \in \mathbb{R}^{m \times n} $$

Linear operations on these groups are still just **addition and subtraction**, applied **element-wise** on matrices of the **same shape**

$$
\begin{bmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    a_{21} & a_{22} & \cdots & a_{2n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
\pm
\begin{bmatrix}
    b_{11} & b_{12} & \cdots & b_{1n} \\
    b_{21} & b_{22} & \cdots & b_{2n} \\
    \vdots & \vdots & \ddots & \vdots \\
    b_{m1} & b_{m2} & \cdots & b_{mn}
\end{bmatrix}
$$
$$
=
$$
$$
\begin{bmatrix}
    a_{11} \pm b_{11} & a_{12} \pm b_{12} & \cdots & a_{1n} \pm b_{1n} \\
    a_{21} \pm b_{21} & a_{22} \pm b_{22} & \cdots & a_{2n} \pm b_{2n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{m1} \pm b_{m1} & a_{m2} \pm b_{m2} & \cdots & a_{mn} \pm b_{mn}
\end{bmatrix}
$$

### ✖️ Scalar Multiplication

$$ kA \in \mathbb{R}^{m \times n} $$

Its notation shorthand for **repeated addition/subtraction** in matrices is also applied **element-wise** on matrices of the **same shape**

$$
k \cdot
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
=
\begin{bmatrix}
k a_{11} & k a_{12} & \cdots & k a_{1n} \\
k a_{21} & k a_{22} & \cdots & k a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
k a_{m1} & k a_{m2} & \cdots & k a_{mn}
\end{bmatrix}
$$

---

## 📚 Composition of Linear Operations in Matrices

The **composition** of these 2 linear operations are also linear, thus this is the only possible composition

> [!example] Fundamental Composition Form
> **Add** the **scaled** versions—$a_n$—of the **same size matrices**—$B_n$
> $$a_1 B_1 + a_2 B_2 + a_3 B_3 + \dots = C$$

> [!warning] Why POS Is Not a Valid Composition
> While this form is clearly a **Sum of Products (SOP)**, one might ask:
> Why not **Product of Sums (POS)**?
>
> In scalar arithmetic, **POS** expands into **SOP** due to distributivity.
>
> In matrix arithmetic, **POS** is not definable element-wise as it would apply **different scalings to different entries**, thus breaking their **relative proportion to one another**.
> > This is not meaningfully linear in organised groups of numbers.
>
> Matrix Multiplication on the other hand is defined through **SOP** as we will see

---

## 🧮 Dot Product

The simplest case is thus to have matrices of size $1 \times 1$

$$
a_1[b_1] + a_2[b_2] + a_3[b_3] + \dots = c
$$

Which is the same as just

$$
\boxed{
 \phantom{\biggr(}
 a_1 \cdot b_1 + a_2 \cdot b_2 + a_3 \cdot b_3 + \dots = c
 \phantom{\biggr)}
}
$$

> [!tip] Named Operation
> This combined multiplication with addition has a special name called a **dot product**,
>
> It is essentially a **sum of products**, or **SOP**, of related numbers in matrices

> [!note] Why "Dot Product"?
> “Dot Product” is named after the **dot notation** used to describe this **composite operation**
>
> $$A \cdot B$$
>
> An undescriptive name this is

---

## 📚 Generalizing the Dot Product

The general form is thus that this dot product can be done on multiple sets of numbers of that matrix—with the same length

> [!example] Basic Form
> $a_n$ is the $n^{th}$ constant
> $B_n$ is the $n^{th}$ matrix of the same shape
> $C$ is the matrix of the same size as $B$
>$$a_1 B_1 + a_2 B_2 + a_3 B_3 + \dots = C$$

If we want more sets of constants to apply to each matrix $B_m$, we can also add those to $a_n$ and make them matrices as well

> [!example] Generalised Form
> $A_n$ and $B_n$ is the $n^{th}$ matrix of the same shape within their respective matrix groups
> $C$ is a matrix—but we haven't standardised what it's size should be
>$$A_1 B_1 + A_2 B_2 + A_3 B_3 + \dots = C$$

---

## 🧭 Axis and Reading Order

How should the 2 matrices of data be represented?

> [!tip] Axes and Representation
> In order for the **resultant vector** to be **easily traced**, we make one matrix represent one axis and the other matrix represent the other axis
>
> This results in one of the matrix to be comprised of
> > **row matrices**—and therefore read by *row*
>
> And the other to be in
> > **column matrices**—and therefore read by *column*

Now we have to figure out which side the **matrix made of rows** and the **matrix made of columns** should be on

> [!note] Left-Right Arrangement
>
> Since we write equations like so:
>
> $$
> \begin{aligned}
> 2x + 3y &= 8 \\
> 4x + 1y &= 10 \\
> \end{aligned}
> $$
>
> - With coefficients on the left and the single constant on the right
> - Horizontally line-by-line (rows)
> - Stacked vertically (columns)
>
>
> We will continue this trend with:
>
> - **coefficients as rows (left)**
> - **constants as columns (right)**

Thus, we reached a form that is standard for use in matrix multiplication

> [!Example] Standard Form
> **Coefficients matrix** (left) → read by **row**
> **Constants matrix** (right) → read by **column**

---

## 🔵 Dot Product in Matrices

Each entry $c_{ij}$ in the **resultant matrix** is computed as a **dot product** between:

- The **$i^{\text{th}}$ row** of matrix $A$:
  $$
  \vec{a}_{ip} = [a_{i1},\ a_{i2},\ a_{i3}, \cdots,\ a_{ip},]
  $$

- The **$j^{\text{th}}$ column** of matrix $B$:
  $$
  \vec{b}_{pj} =
  \begin{bmatrix}
  b_{1j} \\
  b_{2j} \\
  b_{3j} \\
  \vdots \\
  b_{pj} \\
  \end{bmatrix}
  $$
- Where $p$ is a shared dimension

> [!tip] Matching Elements
> As the **number of elements in the row of the left matrix** must be the **same** as the **number of elements in the column of the right matrix** for **dot product** to work
>
> This is equivalent to just checking the **columns of the left matrix** and the **rows of the right matrix** respectively

> [!note] Dot Product Entry
> Each **entry** in the **resultant matrix** is represented by this
> $$
> \begin{aligned}
> c_{ij} &= \vec{a}_{ip} \cdot \vec{b}_{pj} \\
> &= a_{i1} \cdot b_{1j} + a_{i2} \cdot b_{2j} + a_{i3} \cdot b_{3j} + \cdots
> \end{aligned}
> $$

---

### 📌 Coefficients Matrix

Each row of the **left coefficients matrix** contributes to each row of the result

$$
\begin{bmatrix}
\textcolor{darkorange}{\boxed{2}} & \textcolor{darkorange}{\boxed{3}} \\
\textcolor{green}{\boxed{4}} & \textcolor{green}{\boxed{1}}
\end{bmatrix}
\cdot
\begin{bmatrix}
\textcolor{darkgray}{5} & \textcolor{darkgray}{6} \\
\textcolor{darkgray}{7} & \textcolor{darkgray}{8}
\end{bmatrix}
=
\begin{bmatrix}
\textcolor{darkorange}{
 \boxed{
  \textcolor{darkorange}{2} \cdot \textcolor{darkgray}{5}
  \textcolor{darkgray}{+}
  \textcolor{darkorange}{3} \cdot \textcolor{darkgray}{7}
 }
}&
\textcolor{darkorange}{
 \boxed{
  \textcolor{darkorange}{2} \cdot \textcolor{darkgray}{6}
  \textcolor{darkgray}{+}
  \textcolor{darkorange}{3} \cdot \textcolor{darkgray}{8}
 }
}\\
\textcolor{green}{
 \boxed{
  \textcolor{green}{4} \cdot \textcolor{darkgray}{5}
  \textcolor{darkgray}{+}
  \textcolor{green}{1} \cdot \textcolor{darkgray}{7}
 }
}&
\textcolor{green}{
 \boxed{
  \textcolor{green}{4} \cdot \textcolor{darkgray}{6}
  \textcolor{darkgray}{+}
  \textcolor{green}{1} \cdot \textcolor{darkgray}{8}
 }
}
\end{bmatrix}
=
\begin{bmatrix}
31 & 36 \\
27 & 32
\end{bmatrix}
$$

### 🎯 Constants Matrix

Each column of the **right constants matrix** contributes to each column of the result.

$$
\begin{bmatrix}
\textcolor{darkgray}{2} & \textcolor{darkgray}{3} \\
\textcolor{darkgray}{4} & \textcolor{darkgray}{1}
\end{bmatrix}
\cdot
\begin{bmatrix}
\textcolor{red}{\boxed{5}} & \textcolor{cyan}{\boxed{6}} \\
\textcolor{red}{\boxed{7}} & \textcolor{cyan}{\boxed{8}}
\end{bmatrix}
=
\begin{bmatrix}
\textcolor{red}{
 \boxed{
  \textcolor{darkgray}{2} \cdot \textcolor{red}{5}
  \textcolor{darkgray}{+}
  \textcolor{darkgray}{3} \cdot \textcolor{red}{7}
 }
}&
\textcolor{cyan}{
 \boxed{
  \textcolor{darkgray}{2} \cdot \textcolor{cyan}{6}
  \textcolor{darkgray}{+}
  \textcolor{darkgray}{3} \cdot \textcolor{cyan}{8}
 }
} \\
\textcolor{red}{
 \boxed{
  \textcolor{darkgray}{4} \cdot \textcolor{red}{5}
  \textcolor{darkgray}{+}
  \textcolor{darkgray}{1} \cdot \textcolor{red}{7}
 }
}&
\textcolor{cyan}{
 \boxed{
  \textcolor{darkgray}{4} \cdot \textcolor{cyan}{6}
  \textcolor{darkgray}{+}
  \textcolor{darkgray}{1} \cdot \textcolor{cyan}{8}
 }
}
\end{bmatrix}
=
\begin{bmatrix}
31 & 36 \\
27 & 32
\end{bmatrix}
$$

---

## 🔮 What is Matrix Multiplication

And thus **Matrix Multiplication** is the **standardised** application of **dot products** where its numbers are **organised** in rows and columns

> [!note] Overview
> Each entry in the result matrix is a **related sum of products**—a dot product—between:
>
> - A **row** from the **left coefficient matrix**
> - A **column** from the **right constant matrix**
>
> Where
>
> - **Number of columns in the left matrix = Number of rows in the right matrix**
