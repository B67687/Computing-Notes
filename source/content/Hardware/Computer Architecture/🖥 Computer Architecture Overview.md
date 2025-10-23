
## 🧠 CPU (Central Processing Unit)
The "brain" of the computer — executes instructions and manages system operations.

### 1️⃣ Control Unit (CU)
- **Role:** Directs the flow of data and instructions.
- **Analogy:** CPU's "CPU" — orchestrates ALU, registers, and memory interactions.

### 2️⃣ Arithmetic Logic Unit (ALU)
- **Role:** Performs all arithmetic and logical operations.
- **Arithmetic Ops:** Add, subtract, multiply, divide.
- **Logic Ops:** Boolean operations — AND, OR, XOR, NAND, NOT, etc.

### 3️⃣ Register Array
- **Role:** Small, ultra‑fast storage inside the CPU.
- **Examples:**
  - **Program Counter (PC):** Tracks the next instruction’s address.
  - **Instruction Register (IR):** Holds the current instruction being executed.
  - **General‑Purpose Registers:** Temporary data storage.
  - **Pointers:** Address references for stack, data, or base.

---

## 🛣 System Bus
Acts as the **information highway** between CPU, memory, and peripherals.

- **Data Bus:** Transfers actual data between components.
- **Address Bus:** Carries memory addresses for read/write operations.
- **Control Bus:** Sends control signals (e.g., read/write commands, clock signals).

---

## 💾 Memory (RAM)
Temporary working storage for programs and data.

- **Basic Unit:** 8‑bit **byte** (2 nibbles).
- **Scaling:** Larger sizes are multiples of bytes.
- **Capacity Measure:** Typically in 2ⁿ bytes (binary addressing).
- **Common Units:**  
  - **KB:** Kilobyte — 10³ bytes (SI standard) or 2¹⁰ bytes (KiB in binary).
  - **MB:** Megabyte — 10⁶ bytes (SI) or 2²⁰ bytes (MiB).
  - **GB:** Gigabyte — 10⁹ bytes (SI) or 2³⁰ bytes (GiB).

---

## 🔄 CPU–Memory–Bus Interaction Flow
1. **CU** fetches instruction address from **PC** via **Address Bus**.  
2. Instruction/data retrieved from **RAM** via **Data Bus**.  
3. **ALU** processes data (math or logic).  
4. Results stored back in register or memory.
