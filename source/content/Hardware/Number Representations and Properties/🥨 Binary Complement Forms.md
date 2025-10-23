
## 🧠 What Are Complements?

Complements are alternate representations of numbers that enable subtraction via addition. They’re used in digital systems to simplify arithmetic operations, especially subtraction and signed number representation.

There are two major types:

- **Diminished Complement**: One less than the full radix complement
- **Non-Diminished (Radix) Complement**: The full complement relative to the base

> Refer to [[🔁 Subtraction Through Addition — Method of Complements| Derivation of Method of Complements]] to understand why

---

## 🔢 Decimal Examples

Let’s use base-10 (decimal) to illustrate:

### 1. Diminished Complement (9’s Complement)

- Defined as: $10^n - 1 - N$
- Example: For 3-digit number 123 → $999 - 123 = 876$
- Used in manual subtraction methods

### 2. Non-Diminished Complement (10’s Complement)

- Defined as: $10^n - N$
- Example: For 3-digit number 123 → $1000 - 123 = 877$
- Enables subtraction via addition with carry discard

---

## 💻 Binary Counterparts

In binary (base-2), these concepts map directly to:

| Decimal Concept       | Binary Equivalent      | Name             |
|-----------------------|------------------------|------------------|
| Radix Complement | $2^n - N$          | **2’s Complement** |
| Diminished Radix Complement | $2^n - 1 - N$          | **1’s Complement** |

> [!NOTE]
> **2's Complement ———— $2^n - N$
>**1's Complement ———— $2^n - 1 - N$
>
> - Thus we notice that:
 > `1's Complement` = `2's Complement` - `1`
> - Or similarly:
 > `2's Complement` = `1's Complement` + `1`

---

## 🔁 1’s Complement (Diminished)

- Operation: **Bitwise inversion** (flip all bits)

> Refer to [[🥨 Binary Complement Form Conversion — Derivation#🔁 1's Complement| Binary Complements Derivation]] to understand why

- Example: `0101` → `1010`
- Used historically in older systems
- Requires **end-around carry** during addition

### Properties

- Two representations of zero: `0000` (+0) and `1111` (−0)
- Subtraction via: $A + (\text{1’s complement of B}) + \text{carry}$

---

## 🔁 2’s Complement (Non-Diminished)

- Operation: **Bitwise inversion + 1**

> Refer to [[🥨 Binary Complement Form Conversion — Derivation#🔁 2's Complement| Binary Complements Derivation]] to understand why

- Example: `0101` → `1010` → `1011`
- Dominant in modern computing
- No need for end-around carry

### Properties

- Single representation of zero: `0000`
- Arithmetic is **bitwise consistent**
- Overflow detection is straightforward
- Enables signed number representation and subtraction using addition

---

## 🧠 Why 2’s Complement Is Preferred

- **Hardware simplicity**: Same adder circuit handles both addition and subtraction
- **No ambiguity**: Only one zero
- **Efficient overflow detection**: Based on carry into and out of MSB
- **Bitwise consistency**: Arithmetic works identically across bit widths

---

## 🧼 Summary Table

| Complement Type       | Formula             | Binary Form        | Notes |
|-----------------------|---------------------|---------------------|-------|
| Diminished (9’s)      | $10^n - 1 - N$      | 1’s Complement      | Requires end-around carry |
| Non-Diminished (10’s) | $10^n - N$          | 2’s Complement      | Preferred in hardware |
| 1’s Complement         | Bitwise NOT         | `~N`                | Two zeros, legacy use |
| 2’s Complement         | `~N + 1`            | `-N`                | Single zero, modern standard |

---

## 🔍 Visual Analogy

Imagine complements as **mirrors**:

- 1’s complement is a **partial mirror**—it reflects the bits but doesn’t shift the frame
- 2’s complement is a **full mirror with offset**—it reflects and nudges the value to complete the inversion

---

## 🧠 Vault Integration Ideas

- Diagram: Bitwise flow of 1’s vs 2’s complement
- Module: Subtraction via complement addition
- Table: Comparison of signed representations across complement systems
- Semantic map: How radix logic generalizes to binary
