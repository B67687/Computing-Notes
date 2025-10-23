## 📘 Overview

A common misconception is that the sum of two irrational numbers is always irrational. This module formalizes a **systematic counterexample technique**—the *Generalized Polarity Trick*—which constructs irrational pairs whose sum is rational via **algebraic cancellation**.

---

## 🔍 Core Insight

> If two irrational numbers contain **equal and opposite irrational components**, their sum cancels the irrationality and yields a **rational result**.

This works regardless of sign, magnitude, or algebraic complexity—so long as the irrational parts cancel and the remaining components are rational.

---

## 🧩 Formal Construction

Let:

- $x = r_1 + j$
- $y = r_2 - j$

Where:

- $r_1, r_2 \in \mathbb{Q}$ (rational)
- $j \in \mathbb{R} \setminus \mathbb{Q}$ (irrational)

Then:

- $x + y = (r_1 + r_2) + (j - j) = r_1 + r_2$ → **rational**

---

## ✅ Rational Closure Justification

- Rational numbers are closed under addition:
  $\frac{a}{b} + \frac{c}{d} = \frac{ad + bc}{bd} \in \mathbb{Q}$
- Integer operations are closed under addition and multiplication
- Therefore, $r_1 + r_2 \in \mathbb{Q}$

---

## 🧪 Audit Examples

| $x$                  | $y$                  | Sum            | Rational? | Notes |
|----------------------|----------------------|----------------|-----------|-------|
| $\sqrt{2}$           | $2 - \sqrt{2}$       | $2$            | ✅        | Positive irrationals |
| $-1 + \pi$           | $3 - \pi$            | $2$            | ✅        | Mixed signs |
| $5 + \sqrt{7}$       | $-2 - \sqrt{7}$      | $3$            | ✅        | Negative irrational cancel |
| $\sqrt{2}$           | $\pi$                | $\sqrt{2} + \pi$ | ❌        | No cancellation |
