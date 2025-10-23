> [!Why we invented it]
> Boolean logic traditionally focuses on **truth-functional primitives** like `AND`, `OR`, and `NOT`.
> But real-world logic often demands **relational conditions**—like detecting **difference** or **equality** between inputs.

### Why "Exclusive"?

- **Exclusivity** means: "Only one input is true."
- This contrasts with **inclusive OR**, which allows both inputs to be true.

> `XOR` captures **mutual exclusivity**: true when inputs differ.
> `XNOR` captures **mutual agreement**: true when inputs match.

### Why `OR` works but not `AND`?

- `AND` is by definition **the opposite of mutual exclusivity** by requiring both inputs to be true.
- `OR` is by definition **inclusive**—true when *either or both* inputs are true.

> This is why we can make `OR` more specific through **mutual exclusivity**, but not `AND`.

---

## 🔍 Gate-by-Gate Semantics

### ➕ `OR` Gate

- **A `OR` B** means:
  → At least one of them is true
  → Inclusive disjunction: `A + B`

> Test if **either** input is **true**

---

### 🚫 `NOR` Gate

- **`NOT` (A `OR` B)** means:
  → Both must be false
  → Complement of `OR`: `(A + B)'` or `A' · B'`

> Test if **all** inputs are **false**

---

### ✖️ `AND` Gate

- **A `AND` B** means:
  → Both must be true
  → Conjunction: `A · B`

> Test if **all** inputs are **true**

---

### 🛑 `NAND` Gate

- **`NOT` (A `AND` B)** means:
  → At least one must be false
  → Complement of `AND`: `(A · B)'` or `A' + B'`

> Test if **either** input is **false**

---

### 🔀 `XOR` Gate

- **A `XOR` B** means:
  → Inputs must differ
  → Exclusive disjunction: `A ⊕ B`

> Test if all inputs are **different**

---

### 🔁 `XNOR` Gate

- **`NOT` (A `XOR` B)** means:
  → Inputs must be the same
  → Logical equivalence: `(A ⊕ B)'` or `A ⊙ B`

> Test if all inputs are the **same**

---

## 🧠 Clarifying `XOR` vs `XNOR`

- `XOR` is not just “only one is true”—it’s more precisely:

> It affirms **difference**

- `XNOR` is not just “not only one is true”—it’s more precisely:

> It affirms **sameness**

---

## 🧪 Boolean Derivations

### `XOR`: Exclusive OR (Difference Check)

- **Canonical Form:**

  ```math
  A ⊕ B = (A · B') + (A' · B)
  ```

- **De Morgan Dual:**

  ```math
  A ⊕ B = ((A' · B)' + (A · B'))'
  ```

- **Truth Table:**

$$
\begin{array}{|c|c|c|}
\hline
A & B & A ⊕ B \\
\hline
0 & 0 & 0 \\
0 & 1 & 1 \\
1 & 0 & 1 \\
1 & 1 & 0 \\
\hline
\end{array}
$$

---

### `XNOR`: Exclusive NOR (Equality Check)

- **Canonical Form:**

  ```math
  A ⊙ B = (A · B) + (A' · B')
  ```

- **Dual Implication Form:**

  ```math
  A ⊙ B = (A + B') · (A' + B)
  ```

- **Truth Table:**

$$
\begin{array}{|c|c|c|}
\hline
A & B & A ⊙ B \\
\hline
0 & 0 & 1 \\
0 & 1 & 0 \\
1 & 0 & 0 \\
1 & 1 & 1 \\
\hline
\end{array}
$$

---

## ✅ Summary Table

| Gate   | Meaning                  | Expression     |
|--------|--------------------------|----------------|
| `OR`     | At least one is true     | `A + B`          |
| `NOR`    | Both must be false       | `(A + B)'`       |
| `AND`    | All must be true         | `A · B`          |
| `NAND`   | At least one is false    | `(A · B)'`       |
| `XOR`    | Inputs must differ       | `A ⊕ B`          |
| `XNOR`   | Inputs must be the same  | `(A ⊕ B)'`       |
