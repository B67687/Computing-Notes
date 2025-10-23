## 🧠 Motivation

> [!Why we need correction]
> Binary-Coded Decimal (BCD) uses 4-bit binary to represent decimal digits $0$–$9$ only.
>
> But binary addition can produce results up to $18$ ($9 + 9$), which is `10010` in binary—**not a valid BCD digit**.
>
> So we need a correction mechanism to:
>
> - Skip invalid BCD codes ($1010$ to $1111$)
> - Propagate carry to the next decimal digit
> - Preserve decimal correctness across multiple digits

---

## 🔢 BCD Digit Range

| Decimal | BCD     | Valid? |
|---------|---------|--------|
| 0–9     | 0000–1001 | ✅ Yes |
| 10–15   | 1010–1111 | ❌ Invalid |

---

## 🔧 Correction Rule

> If the 4-bit sum exceeds $1001$ (i.e., decimal $9$), **add $0110$ (decimal $6$)** to correct it.

### Why Add 6?

- It pushes the sum into the next valid BCD range (`arithmetic modulus`)
- It triggers a carry into the next digit
- It skips the 6 invalid codes ($1010$ to $1111$)

---

## 🧮 Example: $9 + 9$

```plaintext
  1001   (BCD for 9)
+ 1001   (BCD for 9)
-------
 10010   (binary sum = 18)
```

- Lower 4 bits: `0010` (BCD for 2)
- Carry bit: `1` → must propagate

### Apply Correction

```plaintext
 0010 + 0110 = 1000 (BCD for 8)
```

- Carry bit already handled → next digit gets `1`

---

## 🔁 Multi-Digit BCD Addition

For each digit:

1. Add the two BCD digits
2. If result > $1001$, add $0110$
3. If result ≥ $16$ (i.e., 5-bit overflow), propagate carry
4. Repeat for next digit with carry-in

---

## ✅ Semantic Summary

| Step                        | Purpose                          |
|----------------------------|----------------------------------|
| Add BCD digits             | Base operation                   |
| Check if sum > $1001$      | Detect invalid BCD result        |
| Add $0110$ (decimal 6)     | Skip invalid codes, trigger carry|
| Propagate carry            | Maintain decimal correctness     |

---

## 🔗 Vault Integration

- Link to [BCD Encoding Notebook](vault://encoding/bcd-basics)
- Extend with [Decimal Arithmetic Pipeline](vault://arithmetic/decimal-correction)
- Cross-reference [Overflow Detection in BCD](vault://arithmetic/bcd-overflow)

---

## 🧠 Closing Insight

> [!Note]
> BCD addition is not just binary addition—it’s **binary addition with semantic correction**.
> The addition of $6$ is a modular skip over invalid encodings, ensuring that each 4-bit group remains a valid decimal digit.
