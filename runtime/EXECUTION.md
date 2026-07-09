# EXECUTION.md

Status  : LOCKED  
Version : 1.7.0  
Purpose : Menjalankan task berdasarkan Runtime Mode  

---

# Execution Flow

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

# Mode Output Rule

## Mode 0

```text
Answer only.
```

## Mode 1

```text
1. Audit singkat
2. File plan singkat
3. Change summary
4. Validation
5. Final report
```

## Mode 2

```text
1. Audit summary
2. File plan
3. Implementation plan
4. Change summary
5. Validation
6. Docs update
7. Final report
```

## Mode 3

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

## Mode 4

```text
1. Gap
2. Risk
3. Evidence
4. Validation issue
5. Fixing prompt
```

No implementation.

---

# Rule

- Use smallest possible patch.
- Do not add future feature.
- Do not rewrite without evidence.
- Do not change existing behavior unless required.
- Stop after objective completed.

---

# Status

LOCKED
