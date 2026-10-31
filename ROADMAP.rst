.. SPDX-License-Identifier: GPL-2.0-only

=========================
Futya OS Official Roadmap
=========================

:Architecture: AArch64 (64-bit ARM)
:Governance: BDFL
:License: GPLv2 Only

This document outlines the strategic development phases for the Futya OS ecosystem, detailing the linear execution path from low-level bare-metal bootstrap up to the high-level JavaScript application runtime layers.

Phase 1: Bare-Metal Foundation & Hardware Abstraction
=====================================================

The initial milestone focuses on waking the processor and establishing absolute control over physical silicon.

* **Assembly Boot Block (start.S)**
  
  - Drop CPU privileges safely from Exception Level 3/2 (EL3/EL2) down to Exception Level 1 (EL1).
  - Clear and synchronize low-level processor registers.
  - Setup core-isolated Stack Pointers (SP_EL1) for parallel SMP execution.

* **Linker Mapping & Core Alignment (kernel.ld)**
  
  - Define static physical memory entry bounds.
  - Align core code segments (.text, .data, .bss) to 4KB hardware page layout.

* **Exception Vector Table**
  
  - Map the AArch64 synchronous, IRQ, FIQ, and SError vector tables.
  - Implement direct register state caching during hardware traps.

Phase 2: Kernel Core Subsystems (C/C++)
=======================================

Developing the foundational resource-management algorithms.

* **Page-Level Memory Management**
  
  - Initialize the MMU using 4-level page translations (Level 0 to Level 3 structures).
  - Implement strict non-speculative physical page allocation with deterministic depletion tracking.
  - Enforce Execute-Never (XN) bit assignment on user space pools.

* **Symmetric Multiprocessing (SMP) Scheduler**
  
  - Implement deterministic spinlocks to protect cross-core allocation pools.
  - Deploy a parallel Round-Robin task scheduler capable of scaling across 100 emulated cores.

* **High-Velocity Inter-Process Communication (IPC)**
  
  - Structure lock-free bounded ring buffers for zero-copy message passing.
  - Establish strict boundary limits on queue depths to eliminate runtime overcommits.

Phase 3: Android-Inspired Virtual Machine Runtime (Java)
=========================================================

Isolating applications from direct hardware manipulation.

* **Register-Based Bytecode Interpreter**
  
  - Build a compact, lightweight bytecode execution engine operating over virtual registers.
  - Isolate memory context limits for safe app sandboxing.

* **JNI/Native Syscall Bridge**
  
  - Implement the binding layer connecting Java execution blocks to the C++ kernel IPC and allocation handlers.

Phase 4: JavaScript API Bridge & Mobile User Space
===================================================

Providing the high-level application boundary.

* **Embedded JS Engine Porting**
  
  - Integrate a highly compact, sandboxed JS engine into the Java Virtual Machine.

* **System API Definition**
  
  - Expose high-level asynchronous modules for system control and process messaging.
  - Enforce absolute memory boundaries on dynamic string and object instantiation.
