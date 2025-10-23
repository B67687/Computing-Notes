> [!example] Numbers Represented by $n$ Places
> In any positional number system of base $b$, using $n$ places allows representation of exactly $b^n$ distinct values.

## 🎯 Derivation
Counting to from **1 to the maximum value** represented by the number of places is the number represented by the **maximum value of each place**, $b-1$
> $(b-1)b^{n-1} + (b-1)b^{n-2} + \cdots + (b-1)b^1 + (b-1)b^0$

Which is also the same as the place value of the next place minus 1
> $b^n - 1$

Then we count `0` as the unaccounted representation
> $(b^n - 1) + 1$ 

We get
> $b^n$ 

## 📊 Example Table

| Base $b$ | Places $n$ | Range of Values       | Total Count |
|----------|------------|------------------------|-------------|
| 2        | 3          | 000 to 111             | $2^3 = 8$   |
| 10       | 2          | 00 to 99               | $10^2 = 100$ |
| 16       | 4          | 0000 to FFFF           | $16^4 = 65536$ |
