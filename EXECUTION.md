# EXECUTION.md

Status  : LOCKED  
Version : 1.1.0  
Purpose : Menjalankan task berdasarkan Runtime Mode  

---

# EXECUTION FLOW

```text
Boot
↓
Audit
↓
File Plan
↓
Implementation Plan
↓
Implement
↓
Validate
↓
Debug Loop if needed
↓
Knowledge Update
↓
Shutdown
```

---

# MODE OUTPUT RULE

## Mode 0 — Direct

Output:

```text
Answer only.
```

---

## Mode 1 — Micro Patch

Output:

```text
1. Audit singkat
2. File plan singkat
3. Change summary
4. Validation
5. Final report
```

Docs update:

```text
timeline only if needed
current-state only if behavior changed
debug-log if bug loop happened
```

---

## Mode 2 — Feature Patch

Output:

```text
1. Audit summary
2. File plan
3. Implementation plan
4. Change summary
5. Validation
6. Docs update
7. Final report
```

Docs update:

```text
current-state
timeline
audit-gap if any
debug-log if needed
```

---

## Mode 3 — Architecture / Foundation

Output:

```text
1. Full audit
2. Decision log
3. Roadmap / blueprint
4. File plan
5. Implementation plan
6. Validation
7. Full docs update
8. Final report
```

Docs update:

```text
all relevant docs
decision log
architecture
roadmap
current-state
timeline
audit-gap
debug-log if needed
```

---

## Mode 4 — Review Only

Output:

```text
1. Gap
2. Risk
3. Evidence
4. Validation issue
5. Fixing prompt
```

No implementation.

---

# EXECUTION RULE

- Use smallest possible patch.
- Do not add future feature.
- Do not rewrite without evidence.
- Do not change existing behavior unless required.
- Stop after objective completed.

---

# Status

LOCKED
