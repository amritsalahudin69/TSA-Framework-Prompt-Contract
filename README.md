# TSA Framework Prompt Contract

Status  : LOCKED  
Version : 1.7.0  
Scope   : TSA Kernel + Runtime Mode Patch  

---

# Purpose

TSA adalah Engineering Operating System untuk mengatur cara AI bekerja pada project.

Patch ini menambahkan Runtime Mode agar TSA tidak terlalu berat untuk task kecil.

---

# Core Principle

Jangan load seluruh TSA untuk semua task.

Gunakan mode paling ringan yang cukup untuk menyelesaikan objective.

---

# Main Layers

```text
kernel/
  AI Contract

runtime/
  Mode Selector
  Boot
  Execution
  Debug Loop
  Knowledge Update
  Shutdown

prompt/
  Runtime prompt templates

examples/
  Prompt examples / cookbook
```

---

# Runtime Modes

```text
Mode 0 — Direct
Mode 1 — Micro Patch
Mode 2 — Feature Patch
Mode 3 — Architecture / Foundation
Mode 4 — Review Only
```

---

# Read Order

Untuk human:

```text
README.md
runtime/MODE_SELECTOR.md
runtime/BOOT.md
runtime/EXECUTION.md
runtime/DEBUG_LOOP.md
```

Untuk agent:

```text
README for agent.md
runtime/MODE_SELECTOR.md
```

---

# Status

LOCKED
