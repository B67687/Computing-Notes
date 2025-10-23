**Boolean Algebra** is a mathematical system for dealing with binary variables (`0` and `1`) and logical operations

It forms the theoretical foundation of **digital logic design** and **computer architecture**

Invented by **George Boole** in the mid‑1800s, it’s used to:
- Simplify logic circuits
- Model digital systems
- Prove equivalences between logic expressions

---

## 🔤 Boolean Variables & Values

Variables:
> Typically `A`, `B`, `X`, etc.

Values:  
  > $0 \rightarrow$ LOW / FALSE  
  > $1 \rightarrow$ HIGH / TRUE

---

## 🛠 Basic Boolean Operations

| Operation | Symbol(s)  | Logical Meaning | Gate Equivalent | Example |
|-----------|------------|-----------------|-----------------|---------|
| **AND**   | $\cdot$ or no symbol | True only if all inputs are 1 | AND Gate | $A \cdot B$<br><br>or<br><br>$AB$ |
| **OR**    | $+$        | True if at least one input is 1 | OR Gate | $A + B$ |
| **NOT**   | $'$ | Inverts the value | NOT Gate | $A'$ |

---

## 📏 Fundamental Laws

| **Law**             | **Logical Form**                                      | **Boolean Algebra Form**                                 | **Intuition**                                                                 |
|---------------------|--------------------------------------------------------|-----------------------------------------------------------|--------------------------------------------------------------------------------|
| **Identity**        | $A \lor \bot$<br>$= A$<br><br><br><br>$A \lor \top$<br>$= A$ | $A + 0$<br>$= A$<br><br><br><br>$A \cdot 1$<br>$= A$ | `OR INCLUSIVE` with something always `False` is just whatever the original is<br><br>`AND` with something always `True` depends on the state of original |
| **Domination**      | $A \lor \top$<br>$= \top$<br><br><br>$A \land \bot$<br>$= \bot$  | $A + 1$<br>$= 1$<br><br><br>$A \cdot 0$<br>$= 0$  | `OR INCLUSIVE` with anything already `True` is `True`<br><br>`AND` with the anything already `False` is `False` |
| **Idempotent**      | $A \lor A$<br>$= A$<br><br><br>$A \land A$<br>$= A$ | $A + A$<br>$= A$<br><br><br>$A \cdot A$<br>$= A$  | A thing's relationship with itself is still just itself |
| **Absorption**      | $A \lor (A \land B)$<br>$=A$<br><br><br><br><br>$A \land (A \lor B)$<br>$=A$ | $A + (A \cdot B)$<br>$=A$<br><br><br><br><br>$A \cdot (A + B)$<br>$=A$ | Anything `OR INCLUSIVE` something that requires the original to be true, falls back on the original being true<br><br>Anything `AND` something that optionally requires the original to be true, is already just the original  |
| **Consensus**       | $(A \land B)$<br>$\lor (\neg A \land C)$<br>$\lor (B \land C)$<br>$= A \land B$<br>$\phantom{=} \lor (\neg A \land C)$<br><br><br><br>$(A \lor B)$<br>$\land (\neg A \lor C)$<br>$\land (B \lor C)$<br>$= A \lor B$<br>$\phantom{=} \neg (A \lor C)$ | $(A \cdot B)$<br>$+ (A' \cdot C)$<br>$+ (B \cdot C)$<br>$= (A \cdot B)$<br>$\phantom{=} + (A' \cdot C)$<br><br><br><br>$(A + B)$<br>$\cdot (A' + C)$<br>$\cdot (B + C)$<br>$= (A + B)$<br>$\phantom{=} \cdot (A' + C)$ | Redundant terms can be removed when others already cover all cases            |
| **Double-Negation**  | $\neg(\neg A)$<br>$= A$ | $(A')'$<br>$= A$ | Negation brings you to its inverse, do it again and it brings you back |
| **Complement**      | <u>Tautology:</u><br>$A \lor \neg A$<br>$= \top$<br><br><br><u>Contradiction:</u><br>$A \land \neg A$<br>$= \bot$ | <u>Tautology:</u><br>$A + A'$<br>$= 1$<br><br><br><u>Contradiction:</u><br>$A \cdot A'$<br>$= 0$ | <u>Tautology:</u><br>A thing `OR` its opposite is always possible<br><br><br><u>Contradiction:</u><br>A thing `AND` its opposite is impossible at the same time |
| **Commutative**     | $A \lor B$<br>$= B \lor A$<br><br><br>$A \land B$<br>$= B \land A$  | $A + B$<br>$= B + A$<br><br><br>$A \cdot B$<br>$= B \cdot A$ | Order doesn’t affect overall logical relationship |
| **Associative**     | $(A \lor B) \lor C$<br>$=A \lor (B \lor C)$<br>$=B \lor (C \lor A)$<br><br><br>$(A \land B) \land C$<br>$=A \land (B \land C)$<br>$=B \land (C \land A)$ | $(A + B) + C$<br>$=A + (B + C)$<br>$=B + (C + A)$<br><br><br>$(A \cdot B) \cdot C$<br>$=A \cdot (B \cdot C)$<br>$=B \cdot (C \cdot A)$| Grouping doesn’t affect overall logical relationship |
| **Distributive**    | $A \lor (B \land C)$<br>$= (A \lor B)$<br>$\phantom{=} \land (A \lor C)$<br><br><br>$A \land (B\lor C)$<br>$= (A \land B)$<br>$\phantom{=} \lor (A \land C)$ | $A + (B \cdot C)$<br>$= (A + B)$<br>$\phantom{=} \cdot (A + C)$<br><br><br>$A \cdot (B + C)$<br>$= (A \cdot B)$<br>$\phantom{=} + (A \cdot C)$ | Each operation distributes over the other |
| **De Morgan’s**     | $\neg(A \lor B)$<br>$=\neg A \land \neg B$<br><br><br>$\neg (A \land B)$<br>$=\neg A \lor \neg B$ | $(A + B)'$<br>$= A'\cdot B'$<br><br><br>$(A \cdot B)'$<br>$= A' + B'$ | Negation flips between `AND` and `OR` and between `NEGATION` States at the same time |

### 🧩 Idempotent Law

Once a condition is true, repeating it doesn’t make it *truer*.

This law reflects logical identity and guards against redundancy


### 🧲 Absorption and Consensus

Absorption and Consensus is about **redundancy elimination**:
- In `A ∨ (A ∧ B)`, the `A ∧ B` part is already “contained” within A.  
- In `A ∧ (A ∨ B)`, the `A ∨ B` part doesn’t restrict A any further.

This is similar in Consensus Law

### 🔀 DeMorgan’s Law
Apply recursively to nested expressions

> [!example] Correcting a Misperception
> There is a common misperception that these are equivalent
> ```
> (a c′ + c d)' ≠ a′c · c′d′
> ```
>
> Truth is they are different
> ```
> (a c′ + c d)' = (a c′)' · (c d)' = (a′ + c)(c′ + d′)
> ```

---

## 🔄 Duality Principle
Every Boolean expression remains valid if:
- You swap **+** with **·**
- Swap **0** with **1**
This is called **duality**.

Example:
- Law: `A + 0 = A`
- Dual: `A · 1 = A`

---

## ✂️ Simplification Rules
1. Apply **laws** to remove redundant terms.
2. Use **absorption**: `A + (A · B) = A`
3. Use **De Morgan's Theorems**:  
   - ¬(A · B) = ¬A + ¬B  
   - ¬(A + B) = ¬A · ¬B  
1. Aim for minimal number of operations to reduce gate count.