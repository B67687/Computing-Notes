## 🔹 Nibble
- **Bits:** 4  
- **Max value:** 15 (0xF in hex)  
- **Notes:** Fits exactly one hexadecimal digit.

## 🔹 Byte
- **Bits:** 8 (2 nibbles)  
- **Max value:** 255 (0xFF)  
- **Notes:** Standard smallest addressable unit of memory in most systems.

## 🔹 Word
- **Bits:** 16 (2 bytes)  
- **Max value:** 65,535 (0xFFFF)  
- **Notes:** Historically the native register size of older CPUs.

## 🔹 Double Word (DWORD)
- **Bits:** 32 (2 words)  
- **Max value:** ~4.29 billion (0xFFFFFFFF)  
- **Notes:** Common in 32‑bit architectures for registers, addresses, and data.

## 🔹 Quad Word (QWORD)
- **Bits:** 64 (2 double words)  
- **Max value:** ~1.84×10¹⁹ (0xFFFFFFFFFFFFFFFF)  
- **Notes:** Native integer and pointer size in 64‑bit architectures.

---

## 🧩 Relationships
- **nibble → byte → word → dword → qword**  
  `4 → 8 → 16 → 32 → 64` (doubling each step)
- Each step = **×2 width** = **doubles potential representable values**.