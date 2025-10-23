Flowcharts are graphical representations of processes, algorithms, or systems using standardized symbols. They help visualize control flow, decision points, and execution paths in a way that bridges both technical logic and user-facing interaction.

---

## 🔹 Core Purpose

- Clarify the structure and logic of algorithms  
- Aid in debugging, optimization, and documentation  
- Communicate processes across technical and non-technical audiences  
- Separate internal computation from external interaction

---

## 🧱 Basic Symbols

| Symbol        | Meaning                  | Shape Description | Semantic Role |
|---------------|--------------------------|-------------------|----------------|
| ⬬ `Terminal`  | Start / End              | Rounded rectangle | Entry or exit point of the flow<br>- Good to be explicit than to be implicit |
| ⬜ `Process`   | Internal computation or transformation | Rectangle | Represents logic, operations, or function calls |
| 🔷 `Decision`  | Conditional branching    | Diamond           | Evaluates conditions to direct flow<br>(True/False) |
| 🟦 `Input/Output` | External interaction | Parallelogram     | Represents user ↔ system data exchange |
| ➡ `Arrow`     | Flow of control          | Directed line     | Indicates execution sequence |

> [!note] 🧠 Note:  
> `Process` blocks handle internal logic (e.g., calculations, function calls)
> 
> `Input/Output` blocks represent conceptual interfaces—such as user input or system output—not return values or internal data flow.

---

## 🔀 Control Constructs

| Construct   | Description | Flowchart Representation |
|-------------|-------------|---------------------------|
| **Sequence** | Linear execution of steps | ⬜ → ⬜ → ⬜ |
| **Branching** | Conditional logic (if/else) | 🔷 → [Yes] / [No] paths |
| **Looping**   | Repetition based on condition | 🔷 → ⬜ → 🔷 (cycle) |

---

## 🧪 Example: Fever Check Logic

```plaintext
⬬ Start
   ↓
🟦 Input: Enter temperature
   ↓
⬜ Process: Compare with 37.5
   ↓
🔷 Decision: Temp ≥ 37.5?
   ↙           ↘
🟦 Output: Fever   🟦 Output: Normal
   ↓               ↓
⬬ End           ⬬ End
```

## 🧰 Tips for Designing Flowcharts

- ✅ Keep symbols consistent and clearly labeled  
- ✅ Use directional arrows to guide logical flow  
- ✅ Avoid crossing lines—use connectors or off-page references  
- ✅ Modularize complex logic into sub-flowcharts or linked diagrams  
- ✅ Align elements for visual clarity and cognitive ease  
- ✅ Use color or emoji sparingly to highlight key paths or decisions

---

## 🧩 Use Cases

- Algorithm design and debugging  
- System workflows and process automation  
- Business process modeling  
- Educational logic mapping and teaching aids  
- Decision support systems

---

## 🧭 Future Extensions

- [ ] Add hover-tooltips for symbol definitions using callouts or embedded HTML  
- [ ] Embed SVG diagrams for interactive flowchart visualization  
- [ ] Link decision nodes to truth tables or Boolean expressions  
- [ ] Create reusable flowchart templates for algorithmic patterns  
- [ ] Integrate with [[Truth Tables]] and [[Control Flow in Programming]]