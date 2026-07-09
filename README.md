# TSA Runtime Mode Patch

Status  : LOCKED  
Version : 1.1.0  
Scope   : Runtime Layer Only  

---

# Purpose

Patch ini hanya mengubah cara Agent mengonsumsi TSA agar tidak terlalu berat untuk task kecil.

Core TSA tidak diubah.

Sprint 0–9 tetap LOCKED.

AI Contract tetap LOCKED.

---

# Changed Files

```text
README.md
README_FIRST.md
README for agent.md
BOOT.md
EXECUTION.md
DEBUG_LOOP.md
KNOWLEDGE_UPDATE.md
SHUTDOWN.md
examples/expect-prompt-cutting-export.md
```

---

# Main Change

TSA sekarang memakai Runtime Mode.

```text
Mode 0 — Direct
Mode 1 — Micro Patch
Mode 2 — Feature Patch
Mode 3 — Architecture / Foundation
Mode 4 — Review Only
```

Semakin kecil task, semakin ringan TSA yang dibaca.

---

# Core Rule

```text
Do not load all TSA files for every task.
Load only what the selected Runtime Mode requires.
```

---

# Install / Apply

Replace file lama dengan file dalam patch ini.

Rename:

```text
REDME FIRST
```

menjadi:

```text
README_FIRST.md
```

Move:

```text
expect prompt!.md
```

menjadi:

```text
examples/expect-prompt-cutting-export.md
```

---

# Status

LOCKED
