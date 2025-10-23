Understanding how variables behave—how they're typed, bound, and interpreted—is key to mastering programming paradigms. This note explores **static vs dynamic typing**, **variable binding**, and the philosophy of **duck typing**.

---

## 🧩 What Is Variable Typing?

> Typing refers to how a variable’s **data type** is determined, enforced, and checked.

| Typing Mode | Description |
|-------------|-------------|
| **Static Typing** | Type is known and checked at **compile time** |
| **Dynamic Typing** | Type is determined at **runtime**, based on actual value |

---

## 🧱 Static Typing

```text
int x = 5
x = "hello"  ❌ Compile-time error
```
- ✅ Type is declared explicitly (`int`, `float`, etc.)
- ✅ Errors are caught early by the compiler
- ✅ IDEs offer better autocomplete and refactoring
- ❌ Less flexible for generic or polymorphic code

🧠 Languages: C, C++, Java, Rust, Go

---

## 🔄 Dynamic Typing

```text
x = 5
x = "hello"  ✅ Allowed
```

- ✅ No need to declare types  
- ✅ Flexible and concise  
- ❌ Type errors only show up at runtime  
- ❌ Harder to optimize or refactor

🧠 Languages: Python, JavaScript, Ruby, Lua

---

## 🦆 Duck Typing — Behavior Over Type

> “If it walks like a duck and quacks like a duck, it’s a duck.”

Duck typing is a **dynamic typing philosophy** where the **object’s behavior** matters more than its declared type.

```python
def quack_and_walk(thing):
    thing.quack()
    thing.walk()
```
- ✅ No need to check `type(thing)`  
- ✅ As long as `thing` has `quack()` and `walk()`, it works  
- ❌ May cause runtime errors if methods are missing

🧠 Emphasizes **interface by behavior**, not inheritance or type declaration.

---

## 🧠 Variable Binding — Static vs Dynamic

| Binding Type       | Description                                      | Example                        |
|--------------------|--------------------------------------------------|--------------------------------|
| **Static Binding** | Variable type and method calls resolved at compile time | `int x = 5; x.toString()`     |
| **Dynamic Binding**| Resolved at runtime based on actual object       | `x = "hello"; x.upper()`       |

---

## 🧪 Summary Table

| Feature            | Static Typing        | Dynamic Typing        |
|--------------------|----------------------|------------------------|
| Type Known At      | Compile Time         | Runtime                |
| Flexibility        | Low                  | High                   |
| Error Detection    | Early                | Late                   |
| Performance        | Optimized            | Slower (potentially)   |
| Duck Typing        | ❌ Not applicable     | ✅ Core philosophy      |
| Language Examples  | C, Java, Rust        | Python, JS, Ruby       |

---

## 🔗 Related Notes

- [[Type Systems — Nominal vs Structural]]  
- [[Polymorphism — Static, Dynamic, and Duck]]  
- [[Function Overloading vs Duck Behavior]]  
- [[Error Handling in Dynamic Languages]]  
- [[Compile-Time vs Runtime Logic]]

