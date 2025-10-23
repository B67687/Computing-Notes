> [!Why we invented this]
> Canonical notation exists to **standardize Boolean expressions** for truth-table alignment, simplification, and implementation.
>
> It must convey:
>
> - The **function name**
> - The **input variables**
> - The **canonical form type** (SOP or POS)
> - The **term type** (minterm or maxterm)
> - The **truth table indices** that define the function

> Without all five components, the notation risks ambiguity, misinterpretation, or audit failure.

---

### ✅ Canonical Forms – The Only Precise Notation

```plaintext
F(X, Y, Z) = Σm(1, 2, 5, 7)   ← Sum of Minterms (SOP)
F(X, Y, Z) = ΠM(0, 3, 6, 8)   ← Product of Maxterms (POS)
```

> [!Note]
> These forms are:
>
> - **Truth-table aligned**
> - **Gate-synthesis ready**
> - **Audit-friendly**
> - **Universally teachable**

---

### ⚠️ Ambiguous or Incomplete Notations

| Notation             | Problem Description                                  |
|----------------------|------------------------------------------------------|
| `F = Σ(1, 2, 5, 7)`   | No variable context, no term type                   |
| `F = ΣXYZ(1, 2, 5, 7)`| Variable context present, but term type missing     |
| `F = m₁ + m₂ + m₅ + m₇`| Expanded form—fine for synthesis, not canonical     |
| `F(X,Y,Z) = Σ(1,2,5,7)`| Missing term type—ambiguous whether minterms used  |

> [!Audit Flag]
> Canonical notation must be **self-contained** and **unambiguous**.
> Anything less sacrifices semantic integrity.

---

### 🧩 Semantic Breakdown

| Component        | Meaning                                  | Required |
|------------------|-------------------------------------------|----------|
| `F(X,Y,Z)`       | Function name and input variables         | ✅        |
| `Σ` or `Π`       | Canonical form: Sum or Product            | ✅        |
| `m` or `M`       | Term type: minterm or maxterm             | ✅        |
| `(1,2,5,7)`      | Truth table indices                       | ✅        |

---

### 🧠 Visual Analogy

> Think of canonical notation like a **passport**:
>
> - `F(X,Y,Z)` is the name and identity
> - `Σm(...)` or `ΠM(...)` is the visa type (entry or exit logic)
> - The indices are the **countries visited** (truth table rows)
>
> Leave out any part, and the document fails inspection.

---

### ✅ Summary

> ```plaintext
> Canonical SOP:  F(X,Y,Z) = Σm(1,2,5,7)
> Canonical POS:  F(X,Y,Z) = ΠM(0,3,6,8)
> ```
>
> These are the **only semantically complete** forms for canonical Boolean expression.

> [!NOTE]
> Any notation lacking `F(...)`, `Σ/Π`, `m/M`, and truth indices is **non-canonical** and should be flagged for vault exclusion or annotation.
