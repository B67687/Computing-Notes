Adders circuits are foundational in any complex logic circuit

## ⚙️ Half Adder

Adds two single-bit binary inputs: `A` and `B`.

> [!info] Logic Equations
> Sum = $A \oplus B$
> 
> Carry = $A \cdot B$

> [!tip] Notes
> - No carry-in input
> - Cannot be chained directly for multi-bit addition
> - Gate count: 1 XOR, 1 AND

| A | B | Sum (A⊕B) | Carry (A·B) |
|---|---|-----------|-------------|
| 0 | 0 |     0     |      0      |
| 0 | 1 |     1     |      0      |
| 1 | 0 |     1     |      0      |
| 1 | 1 |     0     |      1      |


---

## 🧠 Full Adder

Adds three binary inputs: `A`, `B`, and `Cin` (carry-in).

> [!info] Logic Equations
> Sum = $A \oplus B \oplus C_{in}$
> 
> Cout = $A \cdot B + (A \oplus B) \cdot C_{in}$


> [!tip] Notes
> - Can be chained for multi-bit addition
> - Minimal logic avoids redundancy using XOR
> - Exhaustive logic is more intuitive but less gate-efficient
> - Gate count (minimal): 2 XOR, 2 AND, 1 OR

| A | B | Cin | Sum | Cout |
|---|---|-----|-----|--------|
| 0 | 0 |  0  |  0  |   0    |
| 0 | 0 |  1  |  1  |   0    |
| 0 | 1 |  0  |  1  |   0    |
| 0 | 1 |  1  |  0  |   1    |
| 1 | 0 |  0  |  1  |   0    |
| 1 | 0 |  1  |  0  |   1    |
| 1 | 1 |  0  |  0  |   1    |
| 1 | 1 |  1  |  1  |   1    |

More on [[➕ Full Adder| Full Adders]]