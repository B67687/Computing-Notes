
## 📏 Fundamental Limit

The problem arises because there is no way to have truly continuous monitoring — in real life, sampling happens at **discrete intervals** (although not perfectly discrete either due to the analog nature of electronics).

### ⚡ Ensuring data isn’t lost

- The **receiving clock speed** is intentionally **faster** (oversampling) than the incoming data rate so the receiver can sample at the middle of each bit and avoid timing errors.

## 🔄 Asynchronous Transmission

When transmitted data provides **its own timing cues** (start/stop bits or edges) to the receiver as it arrives, allowing the receiver to **temporarily synchronize** to the incoming data’s timing.

**Why temporarily?**

- Because it is used where the receiver gets data from devices that may each have slightly different timing (clock rates).
- Each burst of data re-synchronizes the receiver for just that burst.

**Typical uses:**

- Where data transfer is **intermittent or irregular**.
- Where **simplicity and compatibility** are more important than raw speed.
- Common in UART serial ports, keyboards, and simple sensors.

- **Note:** Asynchronous is not limited to “many senders” — it can be used between just two devices if the application values flexibility over efficiency.

## ⏱️ Synchronous Transmission

When both sender and receiver are **continuously synchronized** to the same clock signal (either shared directly or embedded in the data stream).

**Why continuous?**

- It allows data to be sent back-to-back with minimal [[📡 Transmission — Extras#🧩 Framing | framing overhead]], making it very efficient for high-speed or large-volume transfers.

**Typical uses:**

- High-speed, high-volume point-to-point links (PCIe, DDR RAM, Ethernet, SATA).

Continuous data streams where resynchronizing each packet would waste too much time.

- **Note:** Synchronous is not limited to just two devices — it can be used in multi-drop buses (like I²C, SPI) as long as all devices share the clock.

## 🔧 Maintaining sync in real life

Perfect synchronization is impossible — clocks drift and signals take time to propagate.

- The solution is **brute-force resynchronization**:
  In **asynchronous**: re-sync at every start bit.
  In **synchronous**: use [[📡 Transmission — Extras#⏰ Phase-Locked Loop (PLL) | phase-locked loops (PLL)]] or embedded clock recovery circuits to continuously adjust alignment — modern hardware does this millions of times per second.

## 📌 TL:DR

- **Asynchronous** = more flexible, lower efficiency, good for irregular data.
- **Synchronous** = more efficient, higher setup cost, good for large/continuous data.
