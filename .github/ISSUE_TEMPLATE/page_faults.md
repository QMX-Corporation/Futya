<!-- .github/ISSUE_TEMPLATE/page_faults.md -->
---
name: "💥 Page Fault Report"
about: Report an unhandled synchronous exception, MMU crash, or translation fault in Futya OS
title: "[PAGE-FAULT]: "
labels: ["bug", "mmu", "triage"]
assignees: dev12124
---

## 🛑 EXCEPTION OVERVIEW
Provide a high-level description of what caused the MMU translation failure.

## 🏁 STEPS TO REPRODUCE
How can we replicate this page fault inside the emulated cluster environment?
1. Build target using: `make TARGET=...`
2. Run command:
3. Observe the crash.

## 📟 HARDWARE REGISTER TELEMETRY
Paste the exact register telemetry captured by GDB or QEMU at the moment of the crash:
* **`FAR_EL1` (Fault Address Register):** 0x...
* **`ESR_EL1` (Exception Syndrome Register):** 0x...
* **`ELR_EL1` (Exception Link Register / PC at fault):** 0x...

## 📊 GDB BACKTRACE
```text
[Paste the complete 'backtrace' or 'thread apply all backtrace' output here]
```

## 💻 ENVIRONMENT INFORMATION
* **Commit Hash:** 
* **QEMU Machine Target:** (e.g., virt, cortex-a53)
