# Bitcoin Scripting: Advanced Stack Arithmetic & Logic

![Language](https://img.shields.io/badge/Language-Bitcoin__Script-orange?style=flat-square&logo=bitcoin)
![Status](https://img.shields.io/badge/Status-Completed-success?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

## 📖 Project Overview
This repository implements a raw **Bitcoin Script** designed to perform on-chain arithmetic operations, percentage-based conditional logic, and cryptographic hashing. The project enforces strict stack manipulation constraints (no high-level abstractions) to demonstrate low-level mastery of the Bitcoin protocol.

**Core Objectives:**
* **Manual Arithmetic:** Summation of input arrays (Student ID digits) directly on the stack.
* **Threshold Logic:** Implementing a **68% comparison check** using integer math.
* **Conditional Execution:** Utilizing `OP_IF/OP_ELSE` to trigger distinct hashing paths based on the logic result.

---

## 📂 Repository Structure
```text
.
├── src/
│   └── script.btc         # The source code with opcode annotations
├── docs/
│   ├── trace_table.png    # Visual execution trace (Step-by-step)
│   └── theory_taproot.md  # Theoretical analysis of Taproot & MAST
├── README.md              # Project documentation
└── LICENSE