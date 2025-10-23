
### 🧠 Motivation

> [!Why we invented this]
> Booth’s algorithm was designed to **optimize signed multiplication** in 2’s complement systems by reducing the number of additions and subtractions.
>
> In traditional binary multiplication, each `1` in the multiplier triggers an addition of the multiplicand. But long runs of `1`s (e.g. `1111`) cause redundant additions.
>
> Booth’s insight: **encode transitions** between bits to compress these operations.
>
> > Instead of reacting to every `1`, we react to **changes** between bits—turning a run of `1`s into a single subtraction followed by a series of shifts.
>
> This makes Booth’s algorithm ideal for hardware, where fewer arithmetic operations mean faster, cheaper computation.

---

## 🔧 Transition Encoding: The Core Trick

Let the multiplier be `Q`, and introduce an extra bit `Q₋₁ = 0`.

We scan the multiplier **bit-pair-wise**: `Qᵢ Qᵢ₋₁`

| Bit Pair | Action                  |
|----------|-------------------------|
| `10`     | Subtract multiplicand   |
| `01`     | Add multiplicand        |
| `00`/`11`| No operation            |

> [!Note]
> This transition encoding compresses runs of `1`s into a single operation, reducing the number of additions/subtractions.

---

## 🧮 Booth’s Multiplication Setup

Let:

- `A` = Accumulator (initially 0)
- `Q` = Multiplier
- `Q₋₁` = Extra bit (initially 0)
- `M` = Multiplicand

We perform `n` cycles (where `n` is the bit-width), and in each cycle:

1. Check `Q₀ Q₋₁` → decide operation
2. Add/Subtract `M` to/from `A`
3. Perform **arithmetic right shift** on `[A Q Q₋₁]`

---

## ⚙️ What It Solves

> [!Success Criteria]
> ✅ Handles signed numbers natively in 2’s complement
> ✅ Reduces redundant additions for long runs of `1`s
> ✅ Uses fewer arithmetic operations than naïve method
> ✅ Preserves sign via arithmetic shifts
> ✅ Avoids separate sign correction logic

---

## ❌ What It Complicates

> [!Tradeoffs]
> ❌ Requires bit-pair scanning logic
> ❌ Needs an extra bit (`Q₋₁`) and accumulator
> ❌ Arithmetic shifts must preserve sign
> ❌ Final result must be interpreted carefully
> ❌ Not intuitive for human learners

---

## 🧮 Worked Example: 1011 × 1101

Let’s multiply `1011` (−5) × `1101` (−3) in 4-bit 2’s complement.

### Step 1: Initial Setup

```plaintext
M = 1011  (−5)
Q = 1101  (−3)
Q₋₁ = 0
A = 0000
```

### Step 2: Cycle Breakdown

| Cycle | Q₀ Q₋₁ | Action         | A       | Q       | Q₋₁ | Notes                        |
|-------|--------|----------------|---------|---------|------|------------------------------|
| 1     | 1 0    | A = A − M      | 0101    | 1101    | 0    | Subtract M                  |
|       |        | Shift          | 0010    | 1110    | 1    | Arithmetic right shift      |
| 2     | 0 1    | A = A + M      | 1101    | 1110    | 1    | Add M                       |
|       |        | Shift          | 1110    | 1111    | 0    | Arithmetic right shift      |
| 3     | 1 0    | A = A − M      | 0101    | 1111    | 0    | Subtract M                  |
|       |        | Shift          | 0010    | 1111    | 1    | Arithmetic right shift      |
| 4     | 1 1    | No operation   | 0010    | 1111    | 1    | No op                       |
|       |        | Shift          | 0001    | 1111    | 1    | Final shift                 |

### Final Result: `00001111` → **+15**

---

## 🧭 Semantic Summary

| Feature                  | Booth’s Algorithm               | Naïve Method                      |
|--------------------------|----------------------------------|-----------------------------------|
| Sign Handling            | Embedded via 2’s complement      | XOR of signs post-multiply        |
| Operation Count          | Reduced via transition encoding | One addition per `1` in multiplier|
| Human Teachability       | ❌ Low                           | ✅ High                            |
| Hardware Efficiency      | ✅ High                          | ❌ Lower                           |
| Final Interpretation     | Requires decoding               | Straightforward                   |

---

## 🧠 Vault Flag: Compression vs Comprehension

Booth’s algorithm is a **compression of signed multiplication logic**, not a conceptual foundation. It’s optimized for **hardware**, not for **human clarity**. For pedagogy, the magnitude-first method is superior.

---

## 🔗 Vault Integration

- Link to [Signed Multiplication Pipeline](vault://arithmetic/signed-mult)
- Extend with [Transition Encoding Map](vault://arithmetic/booth-transitions)
- Cross-reference [2’s Complement Motivation Module](vault://encoding/2s-complement-motivation)
