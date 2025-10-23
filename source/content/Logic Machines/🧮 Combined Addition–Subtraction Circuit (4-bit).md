
Design a unified circuit that performs **binary addition** and **subtraction** using shared logic paths, controlled by a single signal `Add/Sub`.

---

## 🔧 Inputs

| Signal     | Description                            |
|------------|----------------------------------------|
| `x₀`–`x₃`  | 4-bit binary input X                   |
| `y₀`–`y₃`  | 4-bit binary input Y                   |
| `Add/Sub`  | Control signal: `0` → Add, `1` → Sub   |

---

## 🧠 Core Logic

### 1. **XOR Gates as Conditional Inverters**

Each `yᵢ` passes through an XOR gate with `Add/Sub`:

- Logic:
  $yᵢ' = yᵢ \oplus \text{Add/Sub}$
- Behavior:
  - `Add/Sub = 0` → $yᵢ' = yᵢ$ → **Addition**
  - `Add/Sub = 1` → $yᵢ' = \overline{yᵢ}$ → **Subtraction (invert Y)**

> 🔍 Symbol `=1` in the diagram represents XOR with constant 1—nonstandard but semantically valid.

---

### 2. **Initial Carry-In as +1 Offset**

The carry-in to the least significant full adder is also set to `Add/Sub`:

- Logic:
  - `Add/Sub = 0` → carry-in = 0 → **Normal addition**
  - `Add/Sub = 1` → carry-in = 1 → **Adds the +1 needed for two's complement**

Together, this synthesizes:
$X - Y = X + (\overline{Y} + 1)$

---

## 🔄 Full Adder Chain

| Stage | Inputs                     | Output |
|-------|----------------------------|--------|
| FA₀   | `x₀`, `y₀'`, `c₀ = Add/Sub` | `s₀`, `c₁` |
| FA₁   | `x₁`, `y₁'`, `c₁`           | `s₁`, `c₂` |
| FA₂   | `x₂`, `y₂'`, `c₂`           | `s₂`, `c₃` |
| FA₃   | `x₃`, `y₃'`, `c₃`           | `s₃`, `c₄` |

---

## 🧩 Semantic Duality of `Add/Sub`

| Role                  | Mechanism         | Purpose                          |
|-----------------------|------------------|----------------------------------|
| Operand inversion     | XOR gates        | Convert Y to $\overline{Y}$  |
| Two's complement offset | Initial carry-in | Add the +1                       |

This dual use of `Add/Sub` minimizes logic and maximizes audit clarity.

---

## 📐 Notation Audit

| Symbol   | Meaning                  | Notes                             |
|----------|--------------------------|-----------------------------------|
| $\oplus$      | XOR                      | Standard mathematical symbol      |
| `^`      | XOR                      | Common in programming languages   |
| `=1`     | XOR with constant 1      | Diagram-specific shorthand        |

> ⚠️ Recommend replacing `=1` with $ \oplus $ or `^` in vault diagrams for semantic consistency.

---

## 🚨 Overflow Considerations

- Carry-out `c₄` may indicate overflow in signed arithmetic.
- For unsigned operations, overflow occurs if `c₄ = 1` and MSB sum exceeds 1-bit capacity.

---

## 🔗 Extensions

- Generalize to **n-bit ALU** by replicating XOR + FA pattern.
- Integrate with **overflow detection** and **flag registers**.
- Use semantic flags to annotate control flow and operand transformation.
