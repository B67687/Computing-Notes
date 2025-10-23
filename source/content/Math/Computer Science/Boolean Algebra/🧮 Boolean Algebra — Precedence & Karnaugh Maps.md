## 🔢 Operator Precedence (Highest → Lowest)

1. **Parentheses** — evaluate innermost first
   `F = (A + ¬B) · C`
2. **NOT / Complement (¬)**
   `F = A + (¬B · C)`
3. **AND (·)** — binds tighter than OR
   `F = A + (B · C)`
4. **OR (+)**
   `F = (A · B) + C`
5. **XOR (⊕)** — usually same as OR unless parenthesized; resolve L→R
   `F = (A ⊕ B) + C`

> 💡 When unsure, add parentheses to lock the intended grouping.

---

## ♻️ Quick Law Reference

- **De Morgan:** ¬(A·B) = ¬A + ¬B | ¬(A+B) = ¬A · ¬B
- **Absorption:** A + (A·B) = A | A · (A+B) = A
- **Duality:** Swap `+ ↔ ·` and `0 ↔ 1`

---

## 🗺️ Karnaugh Map Basics

- **Purpose:** Visual simplification of Boolean functions
- **Gray code order** ensures adjacency means one-bit change
- **Adjacency wraps around** edges and corners

### Layouts

**3‑var \(F(A,B,C)\):**

- Rows: `AB = 00, 01, 11, 10`
- Cols: `C = 0, 1`

**4‑var \(F(A,B,C,D)\):**

- Rows: `AB = 00, 01, 11, 10`
- Cols: `CD = 00, 01, 11, 10`

---

## 📏 Grouping Rules (SOP / POS)

- Group sizes: 1, 2, 4, 8, 16 (powers of 2)
- Larger groups ⇒ fewer literals
- Wrap-around allowed; corners are adjacent
- Cover all 1s (SOP) / 0s (POS); overlaps OK
- **Prime implicants:** Maximal groups; choose a minimal set
- Use don’t‑cares (X) to enlarge groups

---

## 🧪 Example — 4‑var SOP with Don’t‑Cares

**Definition:**
F(A,B,C,D) = Σ m(0,1,2,3,8,9,10,11) + d(5,7)

**4×4 K‑map:**

| AB\CD  | 00 | 01 | 11 | 10 |
|-------:|:--:|:--:|:--:|:--:|
| 00     | 1  | 1  | 1  | 1  |
| 01     | 0  | x  | x  | 0  |
| 11     | 0  | 0  | 0  | 0  |
| 10     | 1  | 1  | 1  | 1  |

**Grouping:**
G1 (8‑cell) → Rows AB = 00 & 10
**Result:** F = ¬B

---

## 🧱 POS Notes

- Plot 0s, group as per SOP rules
- Each group yields sum terms
  Example: A constant 1 ⇒ `(A + …)`; B constant 0 ⇒ `(¬B + …)`
- Convert between forms via De Morgan

---

## 🧠 Checks & Pitfalls

- **Hazards:** Add consensus terms if needed
  Example: AB + ¬AC ⇒ AB + ¬AC + BC
- **Precedence:** ¬ → AND → OR (unless parentheses override)
- **Verification:** Use truth table or SAT check

---

## 🔗 Obsidian Tips

- Keep a blank 4×4 K‑map SVG (`![[kmap-4var.svg|400]]`) for reuse
- Link to: `[[Fundamental Logic Gates]]`, `[[Timing Diagrams]]`
- Store law refs in a `[[Boolean Laws Quickref]]` note for rapid recall
