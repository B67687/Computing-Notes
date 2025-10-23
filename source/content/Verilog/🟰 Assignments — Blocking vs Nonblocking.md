
This notebook explains the difference between **blocking (`=`)** and **nonblocking (`<=`)** assignments in Verilog, with examples, use cases, and best practices for modeling combinational and sequential logic.

---

## 📌 Overview

| Type              | Syntax   | Execution Style         | Use Case                  |
|-------------------|----------|--------------------------|---------------------------|
| **Blocking**      | `=`      | Step-by-step (sequential)| Combinational logic, temporary variables |
| **Nonblocking**   | `<=`     | Parallel (scheduled)     | Sequential logic (flip-flops, registers) |

> [!tip] Why "Blocking" and "Nonblocking"?
>
> These terms come from **software concurrency**, especially in languages like C or Java, where:
>
> - A **blocking call** halts execution until it completes.    
> - A **nonblocking call** allows other operations to proceed in parallel.
>
> Verilog borrowed this terminology to describe how assignments behave **inside procedural blocks** (`always`, `initial`), especially when modeling **sequential logic**.

---

## 🔒 Blocking Assignment (`=`)

- Executes **immediately** in the order written
- **Order of assignments** matter because of this
- Later statements **see updated values**.
- Can cause **race conditions** if used in sequential logic.

### 🧪 Example

```verilog
always @(posedge clk) begin
  a = b;
  b = a;  // b gets the new value of a (which is b) — not intended!
end
```

### 🚫 Pitfall
- This creates unintended behavior because `a` is updated before `b`.

---

## 🔁 Nonblocking Assignment (`<=`)

- **Schedules** updates — all assignments happen **in parallel** at the end of the time step.
- **Order of assignments** does not matter because of this
- Later statements **see old values**.
- Ideal for modeling **flip-flops and registers**.

### 🧪 Example

```verilog
always @(posedge clk) begin
  a <= b;
  b <= a;  // b gets the old value of a — safe and predictable
end
```

### ✅ Benefit
- Ensures consistent behavior across clock cycles.

---

## 🧩 When to Use Each

| Context                  | Use `=` (Blocking)? | Use `<=` (Nonblocking)? |
|--------------------------|---------------------|--------------------------|
| Combinational logic      | ✅ Yes              | ❌ No                   |
| Sequential logic         | ❌ No               | ✅ Yes                  |
| Temporary variables      | ✅ Yes              | ❌ No                   |
| Flip-flop modeling       | ❌ No               | ✅ Yes                  |

---

## 🧠 Best Practices

- Use `<=` for **registers and state machines** inside `always @(posedge clk)` blocks.
- Use `=` for **combinational logic** inside `always @(*)` blocks.
- Never mix `=` and `<=` in the same `always` block — it leads to subtle bugs.
