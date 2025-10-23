
Logic gates are the building blocks of digital electronics.

They process binary inputs (`0` or `1`) to produce a single binary output based on a specific logical function.

The fundamental logic gates are `AND`, `OR` and `NOT`

---

## 1️⃣ AND Gate

An **AND** gate outputs `1` **only if** all its inputs are `1`. Otherwise, it outputs `0`.

### 📊 Truth Table

| Input A | Input B | Output (A • B) |
|---------|---------|----------------|
| 0       | 0       | 0              |
| 0       | 1       | 0              |
| 1       | 0       | 0              |
| 1       | 1       | 1              |

### 📐 Symbol

    A ----| & |
       ---- OUT
    B ----|   |

### 🔍 Notes

- Logical operation: **Multiplication** in Boolean algebra.
- Only true when **all inputs** are true.
- Extendable to more than 2 inputs.

---

## 2️⃣ OR Gate

An **OR** gate outputs `1` if **at least one** input is `1`.

### 📊 Truth Table

| Input A | Input B | Output (A + B) |
|---------|---------|----------------|
| 0       | 0       | 0              |
| 0       | 1       | 1              |
| 1       | 0       | 1              |
| 1       | 1       | 1              |

### 📐 Symbol

    A ----)≥1 )
       ---- OUT
    B ----)   )

### 🔍 Notes

- Logical operation: **Addition** in Boolean algebra.
- True if **any** input is true.
- Used to combine conditions.

---

## 3️⃣ NOT Gate

### 🧾 Definition

A **NOT** gate outputs the **opposite** of its input (inverts it).

### 📊 Truth Table

| Input (A) | Output (¬A) |
|-----------|-------------|
| 0         | 1           |
| 1         | 0           |

### 📐 Symbol

    A ----|>o---- OUT

### 🔍 Notes

- Logical operation: **Negation** in Boolean algebra.
- Often called an **inverter**.
- Only 1 input.

---

## 🧠 Key Takeaways

- **AND, OR, NOT** are the **fundamental** gates; all other logic gates and digital circuits can be built from them.
- Represented mathematically in **Boolean algebra**.
- Implemented physically using **transistors** in integrated circuits.
