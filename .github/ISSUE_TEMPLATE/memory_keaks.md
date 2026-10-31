<!-- .github/ISSUE_TEMPLATE/memory_leaks.md -->
---
name: "🧠 Memory Leak Report"
about: Report persistent memory leaks, orphaned pointers, or tracking failures in Futya OS
title: "[LEAK]: "
labels: ["bug", "memory", "triage"]
assignees: dev12124
---

## 🛑 LEAK DESCRIPTION
Describe where the memory growth or unreleased page allocation was detected.

## 🏁 STEPS TO REPRODUCE
How to force this resource leak inside the testing harness:
1. Boot the kernel version:
2. Execute the workload sequence:
3. Monitor the allocation pools.

## 🔍 VALGRIND OR QEMU/GDB DIAGNOSTICS
Paste the exact leak analysis tracking output here:
* **Valgrind Log Snippet (e.g., definitely lost, indirectly lost):**
* **Kernel Allocation Bitmap Dump (if applicable):**

## 📊 RELEVANT BLOCK TELEMETRY
```text
[Paste any tracking logs or memory block footprints here]
```

## 💻 ENVIRONMENT INFORMATION
* **Commit Hash:** 
