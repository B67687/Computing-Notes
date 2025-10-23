> Assumes 1 byte (8 bits) per addressable unit.

| Address Width | Formula                 | Bytes (exact)                     | Binary Capacity (IEC) | Decimal Capacity (SI) |
|---------------|-------------------------|------------------------------------|-----------------------|-----------------------|
| **16‑bit**    | $2^{16} × 1 \text{B}$              | 65 536 B                           | 64 KiB                | ~65.5 KB              |
| **32‑bit**    | $2^{32} × 1 \text{B}$              | 4 294 967 296 B                    | 4 GiB                 | ~4.29 GB              |
| **64‑bit**    | $2^{64} × 1 \text{B}$              | 18 446 744 073 709 551 616 B       | 16 EiB                | ~18.45 EB             |

---

## 🔹 Notes

- **IEC (Binary)** uses powers of 1024: KiB, MiB, GiB, TiB, PiB, EiB.
- **SI (Decimal)** uses powers of 1000: KB, MB, GB, TB, PB, EB.
- **Why 16 vs 18:**
  - 16 EiB = 2^64 bytes in *binary units*.
  - 18.45 EB = same byte count in *decimal units*.
- To convert bytes → bits: multiply by **8**.
  *Example:* 16 EiB × 8 = 128 Eib (exbibits).

---

## 💡 Quick Conversion Formulas

```text
Bytes_to_Bits  = Bytes × 8
KiB_to_KB      ≈ KiB × 1.024
Binary_to_Dec  ≈ Bytes × (1024^n / 1000^n)
