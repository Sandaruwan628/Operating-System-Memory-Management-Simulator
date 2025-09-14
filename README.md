# OS Memory Management Simulator (Java)

A didactic simulator of virtual-to-physical address translation featuring **Cache**, **TLB**, **Page Table**, and **Main Memory**. It prints a step-by-step trace (hits/misses, addresses, and the retrieved data).

> **Note:** The original class is named `MemoryMangement` (typo kept intentionally to match the provided code). You may keep it as-is or refactor consistently.

---

## 🧭 Overview

~~~mermaid
flowchart LR
    CPU[CPU makes virtual address] --> C[Cache Lookup]
    C -- miss --> T[TLB Lookup]
    C -- hit --> PAB[Physical Base]
    T -- miss --> PT[Page Table Lookup]
    T -- hit --> PAB
    PT --> PAB
    PAB --> M[Main Memory Read (base ⊕ offset)]
~~~

**What it demonstrates**
- Logical (virtual) address generation and split into **pageNumber** and **offset** (1 digit).
- **Cache → TLB → Page Table** lookup chain with hit/miss trace.
- Physical base + offset (string-concatenated for teaching simplicity).
- Retrieving the final value from **main memory**.

---

## 📁 Project Structure

