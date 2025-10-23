### 🧠 Core Insight

- **A XOR B** (`A ⊕ B`) detects **difference** between A and B.
- **A XNOR B′** (`A ⊙ B′`) detects **sameness** between A and the **inverted B**.
- Since B is flipped, the sameness check in XNOR now aligns with the difference check in XOR.

### 🔍 Truth Table Comparison

| A | B | B′ | A ⊕ B | A ⊙ B′ |
|---|---|----|--------|---------|
| 0 | 0 |  1 |   0    |   0     |
| 0 | 1 |  0 |   1    |   1     |
| 1 | 0 |  1 |   1    |   1     |
| 1 | 1 |  0 |   0    |   0     |

✅ The outputs of `A ⊕ B` and `A ⊙ B′` match perfectly.

### 🔧 Algebraic Proof

Start with:
```markdown
A ⊕ B = A·B̅ + A̅·B
