<!-- .github/ISSUE_TEMPLATE/overcommit.md -->
---
name: "📉 Overcommit & OOM Report"
about: Report speculative overcommit vulnerabilities or unhandled allocation exhaustion crashes
title: "[OVERCOMMIT]: "
labels: ["bug", "oom", "triage"]
assignees: dev12124
---

## 🛑 OUT-OF-MEMORY OR OVERCOMMIT DESCRIPTION
Explain how the system allowed an unlawful allocation overbook or why it failed to recover during RAM exhaustion.

## 🏁 STEPS TO REPRODUCE
How to induce this low-memory exhaustion crash:
1. Boot QEMU with limited RAM constraints using: `qemu-system-aarch64 -m 32M ...`
2. Inject the allocation workload vector:
3. Observe the system failure.

## 📊 CRASH TELEMETRY & HANDLER STATE
Provide logs from the internal memory mitigation handlers:
* **State of `handle_allocation_failure` call:**
* **Was `oom_killer_handler` invoked?** [Yes / No]
* **GDB Multiarch Register Stack Dump:**

## 💻 ENVIRONMENT INFORMATION
* **Commit Hash:** 
