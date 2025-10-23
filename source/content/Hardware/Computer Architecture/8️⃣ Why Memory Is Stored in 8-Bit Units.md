Memory is typically stored and addressed in **bytes**, which are 8 bits wide.

This convention balances hardware simplicity, software compatibility, and encoding power.

## 🎯 Motivation

A single bit can only represent two states: $0$ or $1$. That’s too limited for most unit data types. By grouping 8 bits into a byte, we unlock:

- $2^8 = 256$ distinct values
- Enough to represent characters, small integers, control codes, and instruction opcodes
- A general-purpose unit that’s meaningful across hardware and software layers

So yes—**8 bits is the smallest general-purpose unit of memory** that can “entertain” most atomic data types.

## 📊 Comparative Table: Bit Width vs Representational Power

| Width | Values Represented | Typical Use Case                  |
|-------|---------------------|-----------------------------------|
| 1 bit | 2                   | Boolean flags                     |
| 4 bits| 16                  | Hex digits, nibble operations     |
| 8 bits| 256                 | Characters, opcodes, small ints   |
| 16+   | Thousands+          | Larger integers, addresses, floats|
