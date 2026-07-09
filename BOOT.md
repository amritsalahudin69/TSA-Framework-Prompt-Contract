# BOOT.md

Status  : LOCKED  
Version : 1.1.0  
Purpose : Memilih Runtime Mode dan menyiapkan konteks minimum  

---

# BOOT FLOW

```text
Receive Task
↓
Classify Task
↓
Select Runtime Mode
↓
Load Minimum Required Context
↓
Start Execution
```

---

# MODE LOADER

## Mode 0 — Direct

Load:

```text
No TSA load required.
```

---

## Mode 1 — Micro Patch

Load:

```text
docs/pipeline/current-state.md
docs/pipeline/timeline.md
docs/critical/audit-gap.md
target file only
```

---

## Mode 2 — Feature Patch

Load:

```text
current-state.md
timeline.md
audit-gap.md
architecture.md if relevant
target module
direct dependencies
```

---

## Mode 3 — Architecture / Foundation

Load:

```text
TSA Core
AI Contract
Workflow
Prompt Standard
Project Standard
Current State
Timeline
Decision Log
Architecture
Relevant Docs
```

---

## Mode 4 — Review Only

Load:

```text
current-state.md
agent output
target file / patch
reference docs if needed
```

---

# BOOT RULE

Do not load more than required by selected mode.

If extra file is needed, write:

```text
NEED_FILE:
path:
reason:
```

---

# BOOT FAILURE

Boot dianggap gagal jika:

- mode tidak dipilih
- langsung full repo scan
- membaca file tidak relevan
- implementasi dimulai sebelum context minimum tersedia

---

# Status

LOCKED
