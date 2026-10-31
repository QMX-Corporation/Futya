<!-- .github/ISSUE_TEMPLATE/bug_report.md -->
---
name: "🐛 Bug Report"
about: Report a failure, panic, leak, or unexpected behavior in Futya OS
title: "[BUG]: "
labels: ["bug", "triage"]
assignees: dev12124
---

## 🛑 DETAILED CRASH OR FAILURE DESCRIPTION
Provide a rigorous technical explanation of what failed in the system.

## 🏁 HOW TO REPRODUCE
Steps to replicate the failure inside the development environment:
1. Launch the devcontainer or Docker environment.
2. Build target compilation using: `make TARGET=...`
3. Run the specific test vector or application command:
4. Observe the failure.

## 📊 TELEMETRY & EMULATOR LOGS
Paste the exact output from the toolchain or logs here:
* **QEMU Log Output:**
* **GDB Multiarch Backtrace:**
* **Valgrind Core Dump / Leak Trace:**

## 🎯 AFFECTED SUBSYSTEM
Check the core components affected by this bug:
- [ ] Assembly Boot / HAL
- [ ] C++ Memory Manager (MMU / Translation Tables)
- [ ] C++ Process Scheduler
- [ ] C++ IPC (Inter-Process Communication)
- [ ] Java Virtual Machine Runtime
- [ ] JavaScript API Bridge

## 💻 DEVELOPMENT ENVIRONMENT ENVIRONMENT
* **Host OS:** (e.g., Ubuntu 24.04, Windows 11 WSL2)
* **Commit Hash:** 
