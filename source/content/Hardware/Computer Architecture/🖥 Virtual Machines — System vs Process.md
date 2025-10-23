
## 📜 Overview
A **Virtual Machine (VM)** is a software emulation of a machine that executes programs as if it were actual hardware.  
The term *VM* can mean two different things depending on context:  
- **System VM** → full computer emulation (often used for OS isolation and security).  
- **Process VM** → language/runtime‑level emulation for running bytecode.

---

## 🏛 Types of Virtual Machines

### 🖧 System Virtual Machine
**Purpose:**  
- Emulates an entire physical computer, including CPU, memory, storage, and devices.  
- Allows multiple *full* operating systems to run on the same host machine in isolated environments.

**Key Traits:**  
- Managed by a **hypervisor** (software layer controlling VM instances).  
- Full OS boot process inside the VM.  
- Used for OS isolation, testing, cloud instances, and security sandboxes.

> [!tip] Tip
> #### 🔑 Role of the Hypervisor
> - Acts as the control layer between **host hardware** and **guest operating systems**.
> - Allocates CPU, memory, storage, and network resources across VMs.
> - Enforces **isolation** between VMs for stability and security.
> - Can run:
>  - **Type 1 (bare-metal)** → runs directly on hardware (e.g., VMware ESXi, Microsoft Hyper‑V).
>  - **Type 2 (hosted)** → runs as an app within a host OS (e.g., VirtualBox, Parallels Desktop).
>
> **Flow**:  
> `Physical Hardware → Hypervisor → Virtual Hardware Layer → Guest OS → Applications`
>
> 📌 *Without the hypervisor, the VM wouldn’t have a virtual “hardware stage” to run its OS.*

**Examples:**  
- VirtualBox  
- VMware Workstation / ESXi  
- Hyper‑V  
- QEMU

---

### ⚙️ Process Virtual Machine
**Purpose:**  
- Provides a platform‑independent runtime environment for a **single program**.  
- Executes **bytecode** instructions designed for a virtual CPU.

**Key Traits:**  
- Exists only while its process runs.  
- Focuses on portability, security, and runtime services like garbage collection.  
- Can **interpret** bytecode or **JIT‑compile** it to native code.

**Examples:**  
- JVM (Java Virtual Machine)  
- .NET CLR (Common Language Runtime)  
- CPython (Python’s VM)  
- Lua VM

---

## 🔍 Why Languages Use Process VMs
- **Portability** — “Write once, run anywhere.”  
- **Security** — Bytecode verification before execution.  
- **Optimization** — JIT compilation of hot code paths for current hardware.  
- **Runtime services** — Memory management, threading, exception handling.  
- **Language flexibility** — Multiple languages target the same VM.

---

## 🗺 Quick Comparison

| Feature               | System VM                       | Process VM                     |
|-----------------------|----------------------------------|---------------------------------|
| **Scope**             | Whole OS + hardware             | Single program/runtime         |
| **Isolation**         | Complete OS‑level isolation     | Sandboxed execution inside host|
| **Startup**           | Boots an OS                     | Starts with program            |
| **Performance**       | Near‑native with hardware assist| Varies (interpreted or JIT)    |
| **Examples**          | VirtualBox, VMware, Hyper‑V     | JVM, CLR, CPython              |

---

## 🧩 Relation to Bytecode
In a **process VM**, bytecode is the VM’s *native language* — it’s standardized, platform‑neutral, and easier for the VM to parse and optimize than high‑level source code.

Flow:  
**Source Code** → **Bytecode** → **VM** (interpret or JIT) → **Machine Code** → **CPU**
