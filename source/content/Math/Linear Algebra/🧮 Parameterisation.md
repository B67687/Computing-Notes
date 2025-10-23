When solving systems of equations, we often encounter **dependent relationships** between variables. One variable may be expressed in terms of another, which we call a **free variable**.

---

## 🔁 Direct Relationship

Suppose we solve a system and get:

$$
x = 2y + 3
$$

Here, $y$ is the **free variable**. To evaluate the solution:

- ✅ Assign a value to $y$
- ✅ Compute $x$ using the expression

This works, but it’s **not ideal for generalisation**.

---

## 🎯 Argument–Parameter Clarity

To make the **argument–parameter relationship** explicit, we introduce a new variable (say $a$ or $t$) as the **parameter**:

$$
\begin{align}
x &= 2a + 3 \\
y &= a
\end{align}
$$

Now it's clear:

- $a$ is the **argument** we plug in
- $x$, $y$ are **computed from** $a$

> [!tip]
> This is called the **parametric form**.
>
> Which expresses the solution set as a function of one or more free parameters.
>
> It’s ideal for generalisation, manipulation, and geometric interpretation.

---

## 🧠 Why Use Parametric Form?

Linear algebra emphasizes **general solutions** over specific ones. Parametric form helps:

- 🔍 Clarify dependencies
- 🔄 Plug in arbitrary values
- 🧩 Represent infinite solution sets
- 📐 Interpret geometrically (lines, planes, etc.)

---

## ✅ Best Practice

Always convert solution sets into **parametric form** when:

- You have free variables
- You want to describe the entire solution space
- You’re preparing for geometric or algebraic manipulation
