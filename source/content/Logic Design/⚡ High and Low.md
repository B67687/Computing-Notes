
In digital systems, signals are often described as **High** or **Low**. 

---

## 🔌 Electrical Voltage Levels

At their core, **High** and **Low** refer to **voltage regions**

| Term   | Electrical Meaning | Typical Voltage Range (5V logic) |
|--------|--------------------|-------------------------------|
| **High** | Elevated voltage (near Vcc) | ~2V to 5V |
| **Low**  | Grounded voltage (near GND) | ~0V to 0.8V |

These are **physical descriptors**:
- **High** means the signal line is carrying a voltage close to the positive supply rail.
- **Low** means the signal line is close to ground.

They do **not** inherently mean `1` or `0`—those meanings are assigned by context.

---

## 🗺️ Mapping Voltage to Logic

To interpret High/Low as binary values, we need to know the **signal’s polarity**:

| Signal Type   | High Voltage Means… | Low Voltage Means… |
|---------------|---------------------|---------------------|
| **Active-High** | Asserted / TRUE / `1` | Deasserted / FALSE / `0` |
| **Active-Low**  | Deasserted / FALSE / `0` | Asserted / TRUE / `1` |

So:
- **High voltage always means elevated potential**
- But whether that means `1` or `0` depends on whether the signal is **active-high** or **active-low**