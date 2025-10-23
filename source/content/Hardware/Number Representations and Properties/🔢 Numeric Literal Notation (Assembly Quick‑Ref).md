
## 📍 Common Suffixes (Intel‑Style)

| Suffix | Base / Meaning        | Example   | Decimal Value | Notes |
|--------|-----------------------|-----------|---------------|-------|
| `h`    | Hexadecimal (base‑16) | `4Ah`     | 74            | Add a leading `0` if starting with `A–F` → `0Ah` |
| `b`    | Binary (base‑2)       | `1010b`   | 10            | Rare in older docs, common in MASM/NASM |
| `o` or `q` | Octal (base‑8)    | `77o` / `77q` | 63       | `o` and `q` depend on assembler |
| _(none)_ | Decimal (base‑10)   | `42`      | 42            | Default unless specified |

---

## 💡 Prefix Alternatives

| Prefix | Meaning / Syntax Origin | Example   | Decimal Value |
|--------|-------------------------|-----------|---------------|
| `0x`   | Hex (C‑style)           | `0x4A`    | 74            |
| `$`    | Hex (GAS/AT&T style)    | `$4A`     | 74            |
| `%`    | Binary (GAS style)      | `%1010`   | 10            |

---

## 🛠 Assembler Quirks

- **MASM/TASM:** Strict `h`, `b`, `o` usage; needs a leading `0` if the hex value starts with a letter.
- **NASM/FASM:** Accepts both suffix (`h`) and C‑style (`0x`) notations.
- **GAS (GNU Assembler):** Prefers `$` for constants (AT&T style), no `h` suffix.

---
