A **latch** is a bistable circuit that stores one bit of data. It is **level-sensitive**, meaning its output can change as long as the control signal (often called "enable") is active.

## ⚙️ Key Characteristics
- 🧮 **Memory**: Stores a binary state (`0` or `1`)
- 🔓 **Level-sensitive**: Responds continuously while enabled
- ⏱️ **Asynchronous**: Can change state without a clock edge

## 🔤 Common Types
| 🔧 Type     | 🔢 Inputs       | 📈 Behavior                          |
|------------|----------------|--------------------------------------|
| SR Latch   | Set, Reset     | Sets or resets output                |
| Gated SR   | Set, Reset, Enable | Adds control gating             |
| D Latch    | Data, Enable   | Captures input when enabled          |

## 🧮 SR Latch Logic (NOR-based)
- ✅ **Set = 1, Reset = 0** → Output = 1
- ❌ **Set = 0, Reset = 1** → Output = 0
- 🔁 **Set = 0, Reset = 0** → Holds previous state
- ⚠️ **Set = 1, Reset = 1** → Invalid (undefined)

## 🧰 Use Cases
- 🗂️ Temporary storage
- 🔘 Debouncing switches
- 🧱 Building blocks for flip-flops

## 🪟 Visual Analogy
Imagine a door that opens only when the "enable" signal is held. While open, the latch listens and updates. When closed, it holds its last state.

