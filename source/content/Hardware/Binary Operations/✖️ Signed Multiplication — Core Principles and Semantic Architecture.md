## 🧠 Overview

> [!Summary]
> Signed multiplication in 2’s complement systems behaves like normal multiplication—with a few critical architectural quirks.  
> These quirks arise from modular arithmetic, bit-width constraints, and the encoding of negative values.  
> This notebook documents the four foundational principles that govern signed multiplication.

---

## 🔢 0. Multiplication Is Normal—with Semantic Quirks

- We multiply bitwise as usual: partial products, shifts, and accumulation
- But signed systems introduce:
  - **Sign correction logic**
  - **Bit-width overflow planning**
  - **Negative weight propagation**
- These quirks are not exceptions—they’re **architectural features** of 2’s complement arithmetic

---

## 📏 1. Maximum Bit-Length Is $m + n$

> [!Why this matters]
> Multiplying an $m$-bit number by an $n$-bit number yields a product of **at most $m + n$ bits**

> ### Derivation:
> - Max value of $m$-bit number: $r^m - 1$
> - Max value of $n$-bit number: $r^n - 1$
> - Max product: $(r^m - 1)(r^n - 1) < r^{m+n}$

### Implication:
- Always allocate $m + n$ bits to avoid overflow
- This holds in **any base**, not just binary

---

## 🧮 2. Sign Extension Preserves Value via Modular Arithmetic

> [!Why it works]
> Extending the sign bit (MSB) preserves the value because 2’s complement is a **modular system**

### Formal Insight:
- $x$ in $n$ bits → interpreted modulo $2^n$
- Extend to $m$ bits ($m > n$): replicate MSB
- Value remains congruent modulo $2^m$

### Example:
- $1101_4$ = $-3$
- Sign-extended: $11111101_8$ = still $-3$

> ✅ Sign extension is not a hack—it’s a **modular lift** across bit-width domains

---

## ⚙️ 3. Signed Bit Triggers 2’s Complement Correction

> [!Why we use 2’s complement]
> The signed bit (MSB of multiplier) represents **negative weight**.  
> We can’t multiply it like a normal digit—it contributes a **−2ⁿ** term.

### Correction Strategy:
- Use 2’s complement of multiplicand
- Shift appropriately
- Add/subtract based on sign logic (e.g., Booth’s transitions)

### Semantic Insight:
- 2’s complement lets us **encode subtraction as addition**
- This enables clean accumulation of negative partial products

---

## ✅ Semantic Flags

| Principle                     | Semantic Role                  |
|------------------------------|--------------------------------|
| Normal multiplication        | Structural baseline            |
| Max bit-width $m + n$        | Overflow planning              |
| Sign extension               | Modular integrity              |
| 2’s complement correction    | Negative weight propagation    |

---

## 🔗 Vault Integration

- Link to [Modular Arithmetic Notebook](vault://arithmetic/modular-extension)
- Extend with [Booth’s Algorithm Derivation](vault://arithmetic/booth-logic)
- Cross-reference [Signed Multiplication Pipeline](vault://arithmetic/signed-mult)
- Flag [Bit-width Planning Node](vault://arithmetic/bit-growth)

---

## 🧠 Closing Reflection

> [!Note]
> Signed multiplication is not a mystery—it’s a modular, bit-precise system with elegant correction logic.  
> Once you separate **magnitude logic** from **sign logic**, the architecture becomes teachable, extensible, and audit-ready.

