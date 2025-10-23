This notebook outlines best practices for writing clean, modular, and synthesis-friendly Verilog code—plus common traps and bad habits to avoid. Ideal for collaborative environments, semantic audits, and vault-grade pedagogy.

---

## ✅ Best Practices

You should follow these practices

### 🔤 Descriptive and Mnemonic Naming

- Use meaningful names for modules, ports, and signals.
- Example: `carry_out` instead of `co`, `sum` instead of `s`.

---

### 🧩 Favor Named Instantiation

- Improves readability and reduces port-order errors.

```verilog
add_half M1 (.a(A), .b(B), .sum(w1), .cout(w2));
```

---

### 🧱 Modular Design

- Break logic into reusable submodules.
- Use parameters for scalable designs.

```verilog
module adder #(parameter WIDTH = 8) (...);
```

---

### 🎨 Consistent Formatting

- Align declarations and logic blocks.
- Use consistent indentation for visual clarity.

---

### ⏰ Use Clocked Always Blocks

- Prefer `always @(posedge clk)` for sequential logic.
- Avoid [[📑 Verilog Syntax Reference#🔄 Conditional Statements| latch inference]] from incomplete conditions.

---

### 🔄 Explicit Reset Logic

```verilog
always @(posedge clk or posedge reset) begin
  if (reset)
    state <= IDLE;
  else
    state <= next_state;
end
```

---

### 🔁 Use Non-Blocking Assignments for Sequential Logic

- Use `<=` in clocked blocks.
- Use `=` only for combinational logic.

---

### 🧬 Signal Assignment Discipline

- If a signal is assigned inside an `always` block, **do not assign it anywhere else**.
- Avoid mixing `assign` statements or multiple `always` blocks for the same signal.
- Each `always` block should own its assigned signals exclusively.
- Group signals into a single block only if they follow similar logic.

```verilog
always @* begin
  x = a & b;  // x assigned here
  y = a | b;
end

// ❌ Don't do this elsewhere:
assign x = something_else; // Conflicting driver
```

---

### 📐 Statement Order Matters in `always` Blocks

- Statements inside an `always` block are executed **in order**, top to bottom.
- If a signal is assigned multiple times, **the last assignment wins**.
- Synthesis tools collapse this into combinational logic, but the order defines the final behavior.

```verilog
always @* begin
  y = a & b;
  y = x | c;  // This overrides the previous y
  x = ~c;
end
```

- **Best Practice**: Avoid reassigning the same signal within a block unless intentional.
- **Pedagogy**: Reinforces the difference between procedural flow and hardware mapping.

---

### 💬 Strategic Commenting

- Explain non-obvious logic and edge cases.
- Avoid redundant comments.

---

### 🔢 Avoid Magic Numbers

- Use `parameter` or `localparam` for constants.

```verilog
parameter WIDTH = 8;
```

---

### 🧪 Simulate Before Synthesis

- Write testbenches to verify behavior.
- Use assertions and waveform inspection.

---

### 🚫 Avoid Vendor-Specific Constructs

- Stick to synthesizable, portable Verilog.
- Avoid `initial` blocks unless targeting specific FPGAs.

---

### 🧭 Use Case Defaults

- Always include a `default:` case to prevent unintended behavior.

---

### 📑 Document Module Interfaces

- Include comments or headers for module purpose, inputs, and outputs.

---

### 🛠️ Audit Synthesis Logs

- Review for inferred latches, unused signals, or resource-heavy constructs.

---

## ❌ Bad Practices & Traps to Avoid

You should avoid these practices

### ⚠️ Vector Width Mismatches

```verilog
wire [3:0] a;
assign a = 5; // ❌ RHS is 3'b101, not 4 bits
```

---

### ⚠️ Unintended Latch Inference

```verilog
always @(a or b)
  if (a) y = b; // ❌ No else → latch inferred
```

---

### ⚠️ Mixed Blocking and Non-Blocking Assignments

- Mixing `=` and `<=` in the same `always` block leads to race conditions.

---

### ⚠️ Ambiguous Signal Driving

```verilog
assign x = a;
assign x = b; // ❌ Multiple drivers
```

---

### ⚠️ Overuse of `assign` for Sequential Logic

- `assign` is for combinational logic only. Use `always` for sequential behavior.

---

### ⚠️ Missing Sensitivity List Entries

```verilog
always @(a) y = a & b; // ❌ Missing b
```

---

### ⚠️ Using `initial` for Synthesis

- `initial` blocks are not synthesizable in most ASIC flows.

---

### ⚠️ Case-Sensitivity Errors

- Verilog is case-sensitive. `Sum` ≠ `sum`.

---

### ⚠️ Implicit Net Declarations

- Avoid undeclared wires. Use `default_nettype none` to catch these.

---

## 🧠 Summary Table

| Practice / Pitfall               | Impact                                |
|----------------------------------|----------------------------------------|
| Named instantiation              | ✅ Semantic clarity                     |
| Vector width mismatch            | ❌ Synthesis errors                     |
| Latch inference                  | ❌ Unintended memory behavior           |
| Mixed blocking/non-blocking      | ❌ Race conditions                      |
| Multiple drivers                 | ❌ Undefined behavior                   |
| Statement order in `always`      | ✅ Defines final logic behavior         |
| Strategic commenting             | ✅ Improves teachability                |
| Simulation before synthesis      | ✅ Functional verification              |
| Signal ownership in `always`     | ✅ Prevents driver conflicts            |
