## 📜 Definition
Bytecode is a **platform‑independent, low‑level instruction set** generated from high‑level source code.  
It’s designed to be executed by a **process virtual machine** (VM) rather than directly by a CPU.

---

## 🔄 Where It Fits in the Execution Flow
**Source Code** → **Compiler/Translator** → **Bytecode** → **VM** (interpret or JIT) → **Machine Code** → **CPU**

---

## 🧠 Key Characteristics
- **Intermediate Representation (IR)** — Sits between human‑readable code and CPU‑specific machine code.
- **Standardized Instruction Set** — Often uses 1‑byte opcodes (0–255 possible instructions) plus operands.
- **Portable** — Same bytecode runs on any platform with the right VM.
- **Efficient for VMs** — Already parsed and semantically analyzed, so faster to interpret than raw source.

---

## 🛠 How It’s Executed
1. **Interpretation** — VM reads and executes bytecode instructions one by one.
2. **JIT Compilation** — VM compiles frequently used (“hot”) bytecode paths into native machine code at runtime for speed.

---

## 🔍 Examples
- **Java** → `.java` → `.class` bytecode → JVM
- **.NET** → C# → CIL (Common Intermediate Language) → CLR
- **Python** → `.py` → `.pyc` bytecode → CPython VM
- **Lua** → `.lua` → Lua bytecode → Lua VM

---

## 🛡 Advantages
- **Portability** — “Write once, run anywhere” (with the right VM).
- **Security** — VM can verify and sandbox code before execution.
- **Optimization** — JIT can adapt code to the current hardware.
- **Multi‑language Support** — Different languages can target the same VM.

---

## ⚖️ Bytecode vs Machine Code

| Feature              | Bytecode                              | Machine Code                       |
|----------------------|---------------------------------------|-------------------------------------|
| **Target**           | Virtual Machine                       | Physical CPU                        |
| **Portability**      | High (VM‑dependent)                   | Low (CPU/OS‑specific)               |
| **Execution**        | Interpreted or JIT‑compiled by VM      | Directly executed by CPU            |
| **Optimization**     | Runtime (JIT)                         | Compile‑time                        |
| **Security**         | VM sandbox + verification             | Relies on OS/hardware protections   |

---

## 📌 Related Notes
- [[Virtual Machines — System vs Process]]
- [[Just‑In‑Time Compilation]]
- [[Machine Code]]


## 🔤 Bytecode / Disassembly Suffix Legend

When viewing bytecode in a disassembler, suffix letters often indicate the **data type** or **width** of an immediate value or operand.  
These suffixes are **not** stored in the bytecode itself — they are for human‑readable notation.

| Suffix | Type / Width               | Bits | Example     | Meaning in context                         |
|--------|-----------------------------|------|-------------|---------------------------------------------|
| `b`    | **byte** (signed/unsigned)  | 8    | `10b`       | Literal fits in one byte                    |
| `s`    | **short**                   | 16   | `300s`      | 16‑bit integer                              |
| `i`    | **int**                     | 32   | `1024i`     | 32‑bit integer                              |
| `l`    | **long**                    | 64   | `999999l`   | 64‑bit integer                              |
| `f`    | **float**                   | 32   | `3.14f`     | 32‑bit IEEE‑754 floating point              |
| `d`    | **double**                  | 64   | `2.71828d`  | 64‑bit IEEE‑754 floating point              |
| `z` / `bool` | **boolean**           | 8*   | `1z`        | Boolean (true/false), encoded as 0/1 byte   |
| `c`    | **char** (UTF‑16 code unit) | 16   | `65c`       | Character literal (‘A’)                     |

> **Note:** Exact suffix sets vary by VM, language, or disassembler.  
> For example, `javap` shows some typed constants with suffixes, while others rely on context from the constant pool.

---

### 📌 How to Use This Legend
- Speeds up **reverse‑engineering**: quickly infer the operand’s size/type without checking spec.
- Helpful for **cross‑VM study**: not all VMs use the same suffix convention.
- Useful in **debug notes** alongside opcode meaning.
