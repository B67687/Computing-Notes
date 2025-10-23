
## 🔍 Motivation
In Boolean algebra, grouping adjacent 1s in a Karnaugh map (K-map) simplifies expressions by eliminating variables. But not all group sizes are valid. While even numbers might seem sufficient, only **powers of 2** guarantee full logical reduction. This noteblock flags the distinction and explains why grouping by powers of 2 is essential.

---

## ❌ Misconception: “Even numbers are enough”

- A group of 6 cells is even, but **invalid**.
- Boolean simplification requires **structural symmetry**, not just arithmetic parity.
- Example: $6 = 2 \times 3$ → the leftover factor of 3 breaks the reduction pattern.

---

## ✅ Correct Rule: Group sizes must be powers of 2

| Group Size | Valid? | Reason                          |
|------------|--------|----------------------------------|
| 1          | ✅     | No variables eliminated          |
| 2          | ✅     | 1 variable eliminated            |
| 4          | ✅     | 2 variables eliminated           |
| 8          | ✅     | 3 variables eliminated           |
| 6          | ❌     | Cannot be factored cleanly       |
| 3          | ❌     | No consistent adjacency pattern  |

---

## 🧩 Why powers of 2 work

- Only powers of 2 preserve adjacency and symmetry needed for factoring.
