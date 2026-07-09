# DEBUG_LOOP.md

Status  : LOCKED  
Version : 1.1.0  
Purpose : Memaksa Agent memperbaiki bug setelah validation gagal  

---

# DEBUG LOOP FLOW

```text
Validation
↓
Bug Found?
├── No → Knowledge Update
└── Yes
    ↓
Collect Bugs
    ↓
Write Debug Log
    ↓
Classify Bugs
    ↓
Group by Root Cause
    ↓
Fix Highest Priority Bug
    ↓
Validate Again
    ↓
Bug Still Exists?
        ├── Yes → Repeat Loop
        └── No → Knowledge Update
```

---

# MAX LOOP

```text
MAX_DEBUG_LOOP = 5
```

Jika masih gagal setelah 5 loop, stop dan tulis remaining issue.

---

# DEBUG LOG FILE

Agent wajib membuat/update:

```text
docs/pipeline/debug-log.md
```

---

# DEBUG LOG FORMAT

```text
Debug Session:
Task:
Mode:
Validation Run:
Bug Found:
Root Cause:
Fix Applied:
Validation Result:
Remaining Bug:
Status:
```

---

# BUG CLASSIFICATION

```text
Build Error
Runtime Error
Test Failure
UI Behavior Bug
Data Flow Bug
Validation Bug
Integration Bug
Regression
Documentation Gap
```

---

# FIXING PRIORITY

```text
1. Build Error
2. Runtime Error
3. Broken Main Flow
4. Failed Required Trigger
5. Data Flow Bug
6. Validation Bug
7. UI Behavior Bug
8. Documentation Gap
```

---

# RULE

Agent tidak boleh:

- berhenti setelah test gagal
- menyembunyikan bug
- bilang selesai tanpa validation ulang
- fix symptom tanpa root cause
- mengabaikan bug lain yang ditemukan

---

# STOP CONDITION

Debug loop selesai jika:

```text
Required validation passed
Main flow works
No known blocking bug remains
Debug log updated
```

---

# Status

LOCKED
