Sequential circuits rely on memory elements to store and update state. Two fundamental types are **latches** and **flip-flops**.

---

## 🧩 Core Difference

| Feature         | Latch                              | Flip-Flop                          |
|----------------|-------------------------------------|------------------------------------|
| **Triggering** | Level-sensitive (enabled while active) | Edge-triggered (updates on clock edge) |
| **Control**    | Responds to enable signal           | Responds to clock edge             |
| **Timing**     | Transparent while enabled           | Updates only at discrete moments   |
| **Usage**      | Simpler, used in low-speed or gated designs | Preferred in synchronous systems   |

---

## 🔓 Latches

- **Level-sensitive**: Output follows input **while enable is active**.
- **Types**:
  - **SR Latch**: Set-Reset control
  - **D Latch**: Data latch, simpler and safer
- **Behavior**: Transparent when enabled, holds value when disabled.

### Example: D Latch

| Signal | Description |
|--------|-------------|
| **D**  | Data input   |
| **E**  | Enable       |
| **Q**  | Output       |

**Q = D** when **E = 1**
**Q holds** when **E = 0**

---

## 🕒 Flip-Flops

- **Edge-triggered**: Updates only on **rising or falling clock edge**.
- **Types**:
  - **D Flip-Flop**: Most common, stores one bit
  - **JK Flip-Flop**: Versatile, avoids invalid states
  - **T Flip-Flop**: Toggles output
- **Behavior**: Samples input at clock edge, holds until next edge.

### Example: D Flip-Flop

| Signal | Description |
|--------|-------------|
| **D**  | Data input   |
| **CLK**| Clock        |
| **Q**  | Output       |

**Q updates to D** on **rising edge of CLK**

---

## 🧠 Summary

> **Latches** are level-sensitive and update continuously while enabled.
> **Flip-flops** are edge-triggered and update only at clock transitions.
> Flip-flops are preferred in synchronous systems for predictable timing and noise immunity.
