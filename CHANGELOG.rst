.. SPDX-License-Identifier: GPL-2.0-only

=========================
Futya OS Official Changelog
=========================

All notable changes to the Futya OS AArch64 hybrid kernel ecosystem will be documented in this file.
The project adheres to strict low-level engineering tracking.

 - 2026-10-31
====================

Initial repository architecture, repository governance, and aggressive automation infrastructure deployment.

Added
-----

* **Automated CI/CD Validation Suite**
  
  - Created `.github/workflows/ci.yml` for clean multi-branch AArch64 bare-metal compilation verification.
  - Implemented `.github/workflows/memory_leaks.yml` deploying a dual-stage stress engine (Host Valgrind algorithmic check + 500 bare-metal QEMU simulation vectors monitored via GDB).
  - Implemented `.github/workflows/overcommit.yml` to assert zero-speculative allocations under 32MB physical RAM exhaustion constraints.
  - Implemented `.github/workflows/page_fault_validation.yml` tracking synchronous hardware exceptions (FAR_EL1/ESR_EL1 registers) and Execute-Never (XN) hardware protection enforcement.
  - Implemented `.github/workflows/tests.yml` orchestrating a hyper-parallel test framework triggering 10,000 validation vectors simultaneously across 100 emulated processor cores (SMP) via GNU Parallel.

* **Production DevOps & Redundancy Pipelines**
  
  - Deployed Azure Pipelines infrastructure via `.azurepipelines/azure-pipelines.yml` utilizing modular architecture templates (`install-toolchain.yml` and `build-kernel.yml`) for production release staging.

* **Repository Governance & Triage Controls**
  
  - Configured `.github/ISSUE_TEMPLATE/config.yml` blocking raw blank text issues and routing support to GitHub Discussions.
  - Created specialized issue templates: `bug_report.md`, `memory_leaks.md`, `overcommit.md`, `page_faults.md`, and `feature_request.md`.
  - Added repository files to project root following the no-extension/reStructuredText low-level standard: `CONTRIBUTING`, `GOVERNANCE` (decreeing BDFL leadership model), `LICENSE` (GPLv2 Only restriction), `README`, and `ROADMAP.rst`.

* **Repository Security & Environment Isolation**
  
  - Locked cryptographic validation hashes (`hash.txt`) within submodules (`qemu` and `googletest`) to block untrusted upstream dependencies.
  - Added `.dockerignore`, `.editorconfig` (enforcing LF line-endings and 8-space tabs for Assembly), `.gitattributes`, and `.gitignore`.
