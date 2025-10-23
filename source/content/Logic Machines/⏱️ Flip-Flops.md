A **flip-flop** is a bistable circuit that stores one bit of data. It is **edge-triggered**, meaning it changes state only on a clock transition (rising or falling edge).

## ⚙️ Key Characteristics
- 🧮 **Memory**: Stores a binary state (`0` or `1`)
- 📉 **Edge-triggered**: Changes only on clock edge
- 🕰️ **Synchronous**: Controlled by clock signal

## 🔤 Common Types
| 🔧 Type       | 🔢 Inputs             | 📈 Behavior                          |
|--------------|----------------------|--------------------------------------|
| D Flip-Flop  | Data, Clock          | Captures input on clock edge         |
| T Flip-Flop  | Toggle, Clock        | Toggles output on clock edge         |
| JK Flip-Flop | J, K, Clock          | Generalized SR with toggle logic     |

## 🧮 D Flip-Flop Logic
- ⬆️ On rising edge of clock:
  - Output `Q` takes value of input `D`
  - Holds value until next clock edge

## 🧰 Use Cases
- 🗃️ Registers
- 🔢 Counters
- 🎛️ Finite State Machines (FSMs)
- 🚀 Pipeline stages in CPUs

## 📸 Visual Analogy
Imagine a camera that takes a snapshot only when the shutter clicks (clock edge). Between clicks, the image (state) remains frozen.

