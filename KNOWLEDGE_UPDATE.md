# KNOWLEDGE_UPDATE.md

Status  : LOCKED  
Version : 1.1.0  
Purpose : Mengatur update knowledge berdasarkan Runtime Mode  

---

# KNOWLEDGE UPDATE RULE

Update knowledge mengikuti mode.

Jangan update semua dokumen untuk task kecil.

---

# MODE UPDATE MATRIX

| Mode | Required Update |
|------|-----------------|
| Mode 0 | None |
| Mode 1 | debug-log if needed, timeline if needed |
| Mode 2 | current-state, timeline, audit-gap if needed |
| Mode 3 | full docs, decision log, architecture, roadmap, current-state, timeline |
| Mode 4 | review notes / fixing prompt only |

---

# UPDATE FLOW

```text
Validation Passed
↓
Check Mode
↓
Update Required Docs Only
↓
Write Next Step
↓
Shutdown
```

---

# WHAT TO STORE

Store:

- decision
- root cause
- fix summary
- validation result
- reusable lesson
- next step

Do not store:

- long chat
- repeated explanation
- duplicate information
- temporary thought

---

# SINGLE SOURCE RULE

Setiap informasi hanya disimpan pada dokumen yang tepat.

Contoh:

```text
Current state → current-state.md
Timeline → timeline.md
Bug/debug → debug-log.md
Decision → decision-log.md
Architecture → architecture.md
```

---

# Status

LOCKED
