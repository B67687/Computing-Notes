Pseudocode is a way to express algorithms using a blend of natural language and programming structure. It’s not tied to any specific programming language, but it preserves the logical flow and syntax-like clarity of real code.

---

## 🔹 Core Purpose

- Serve as an **intermediate step** between conceptual logic and actual code  
- Express algorithms in a **language-agnostic**, readable format  
- Aid in planning, teaching, and debugging without worrying about syntax errors  
- Translate flowcharts and logic diagrams into structured steps

---

## 🧩 What Pseudocode Is

> “Code-like logic written in informal English.”

| Format Spectrum | Description |
|------------------|-------------|
| **Natural Language** | Fully written-out instructions (e.g., a recipe) |
| **Pseudocode**        | Structured logic with keywords and indentation |
| **Actual Code**       | Language-specific syntax and semantics |

Pseudocode sits in the middle—structured enough to resemble code, but flexible enough to be readable by anyone.

---

## 🧱 Common Pseudocode Constructs

| Concept        | Pseudocode Example         | Description |
|----------------|----------------------------|-------------|
| **Input**      | `INPUT temperature`         | Receive data from user/system |
| **Output**     | `OUTPUT "Fever"`            | Display result |
| **Assignment** | `total ← price × quantity`  | Store computed value |
| **Condition**  | `IF temperature ≥ 37.5 THEN`| Branching logic |
| **Loop**       | `WHILE count < 10 DO`       | Repetition |
| **Function**   | `FUNCTION square(n)`        | Encapsulated logic |
| **Return**     | `RETURN n × n`              | Output from function |

> 🧠 Use `←` or `=` for assignment, depending on your notation preference.  
> Keywords like `IF`, `WHILE`, `FOR`, `RETURN` are often capitalized for clarity.

---

## 🧪 Example: Fever Check in Pseudocode

```text
INPUT temperature

IF temperature ≥ 37.5 THEN
    OUTPUT "Fever"
ELSE
    OUTPUT "Normal"
END IF
