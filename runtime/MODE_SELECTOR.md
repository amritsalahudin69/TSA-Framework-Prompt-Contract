# MODE_SELECTOR.md

Status  : LOCKED  
Version : 1.7.0  
Purpose : Menentukan Runtime Mode sebelum Agent bekerja  

---

# Rule

Gunakan mode paling ringan yang cukup untuk menyelesaikan task.

Jangan memakai mode berat untuk task kecil.

---

# Mode 0 — Direct

Untuk:

- jawaban cepat
- pertanyaan singkat
- non-project task
- rewrite kecil
- translation
- simple command

Load:

```text
No TSA load required.
```

Output:

```text
Answer only.
```

---

# Mode 1 — Micro Patch

Untuk:

- bug kecil
- edit 1–2 file
- typo UI
- tombol mati
- validasi kecil
- mapping kecil
- fix kecil

Load:

```text
docs/pipeline/current-state.md
docs/pipeline/timeline.md
docs/critical/audit-gap.md
file target
```

Output:

```text
1. Audit singkat
2. File plan singkat
3. Patch / perubahan
4. Validation
5. Final report
```

---

# Mode 2 — Feature Patch

Untuk:

- fitur kecil-menengah
- page/component/module minor
- workflow baru terbatas
- integration ringan
- perubahan beberapa file

Load:

```text
docs/pipeline/current-state.md
docs/pipeline/timeline.md
docs/critical/audit-gap.md
docs/doc/architecture.md jika relevan
file target
file dependency langsung
```

Output:

```text
1. Audit summary
2. File plan
3. Implementation plan
4. Implementation
5. Validation
6. Docs update
7. Final report
```

---

# Mode 3 — Architecture / Foundation

Untuk:

- project baru
- blueprint
- perubahan besar
- architecture change
- module foundation
- repository structure
- standard/framework update

Load:

```text
TSA Core
AI Contract
Workflow
Project Standard
Current State
Timeline
Decision Log
Architecture
Relevant docs
Target files
```

Output:

```text
1. Audit lengkap
2. Decision log
3. Roadmap / blueprint
4. File plan
5. Implementation plan
6. Implementation
7. Validation
8. Documentation update
9. Final report
```

---

# Mode 4 — Review Only

Untuk:

- audit hasil agent
- review patch
- cek gap
- cek risiko
- buat fixing prompt
- tanpa coding

Load:

```text
current-state
output agent
file yang direview
reference terkait
```

Output:

```text
1. Review summary
2. Gap
3. Risk
4. Validation issue
5. Fixing prompt
```

---

# Decision Tree

```text
Task non-project?
├── Yes → Mode 0
└── No
    ↓
Bug kecil / edit 1–2 file?
├── Yes → Mode 1
└── No
    ↓
Fitur kecil-menengah?
├── Yes → Mode 2
└── No
    ↓
Project baru / architecture / foundation?
├── Yes → Mode 3
└── No
    ↓
Review only?
├── Yes → Mode 4
└── No → Mode 2 sebagai default aman
```

---

# Status

LOCKED
