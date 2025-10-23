
## 🧮 Definitions

- **Floor Division (`//`)**: Rounds the result of division **toward negative infinity**.
- **Euclidean Division**: Ensures the **remainder is always non-negative**, adjusting the quotient if necessary.

## 🧠 Python Behavior

- Python’s `//` operator performs **floor division**.
- Python’s `%` operator adjusts the remainder to be **non-negative when the divisor is positive**, making it behave like Euclidean division in many cases.

## ✅ Example with Positive Divisor

- `-7 // 3` → `-3`
- `-7 % 3` → `2`
- `-7 = 3 × (-3) + 2` → Matches Euclidean division

## ⚠️ Example with Negative Divisor

- `-7 // -3` → `2`
- `-7 % -3` → `-1`
- `-7 = (-3) × 2 + (-1)` → Not Euclidean (remainder is negative)

## 🧮 Euclidean Quotient Function

```python
def euclidean_quotient(a, b):
    q = a // b
    r = a % b
    return q if r >= 0 else q + 1
```

## ✅ Summary Table

| Case         | Floor Quotient | Euclidean Quotient |
|--------------|----------------|---------------------|
| -7 // 3      | -3             | -3                  |
| -7 // -3     | 2              | 3                   |

## 💡 Final Insight

- Use `//` and `%` together for Euclidean-like behavior when the divisor is positive.
- For consistent Euclidean division regardless of sign, use a custom function like `euclidean_quotient(a, b)`.
- Python’s `//` performs floor division, which may differ from Euclidean division when negative divisors are involved.
- Understanding the distinction helps avoid subtle bugs in modular arithmetic, cryptography, and number theory applications.
