# SHUTDOWN.md

Status  : LOCKED  
Version : 1.1.0  
Purpose : Menutup task dengan final report sesuai Runtime Mode  

---

# SHUTDOWN FLOW

```text
Validation Complete
↓
Debug Loop Complete
↓
Knowledge Update Complete
↓
Final Report
↓
Stop
```

---

# FINAL REPORT BY MODE

## Mode 0

```text
Answer complete.
```

---

## Mode 1

```text
FINAL REPORT:
1. Audit singkat
2. File changed
3. Validation
4. Status
```

---

## Mode 2

```text
FINAL REPORT:
1. Audit summary
2. Files created/modified
3. Implementation summary
4. Validation result
5. Docs updated
6. Residual risk
7. Next step
```

---

## Mode 3

```text
FINAL REPORT:
1. Full audit summary
2. Decision summary
3. Implementation summary
4. Validation result
5. Documentation update
6. Risk
7. Roadmap / next milestone
```

---

## Mode 4

```text
FINAL REPORT:
1. Review summary
2. Gap
3. Risk
4. Fixing prompt
```

---

# STOP RULE

Agent wajib berhenti setelah final report.

Dilarang:

- menawarkan scope tambahan
- mengerjakan task baru
- menambah improvement tanpa diminta
- membuat diskusi panjang

---

# STATUS

WAIT NEXT TASK
