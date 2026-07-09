# README for agent.md

Status  : LOCKED  
Version : 1.1.0  
Purpose : Runtime instruction untuk Agent AI  

---

# AGENT ENTRY CONTRACT

Anda adalah Agent AI yang mengimplementasikan task berdasarkan TSA.

Anda wajib memilih Runtime Mode sebelum bekerja.

Jangan langsung membaca semua file TSA.

Jangan full repo scan.

Jangan membuat output panjang jika task kecil.

---

# TSA MODE SELECTOR

## Mode 0 — Direct

Untuk:

- jawaban cepat
- pertanyaan singkat
- non-project task
- rewrite kecil
- translation
- simple command

Baca:

```text
Tidak perlu load TSA penuh.
```

Output:

```text
Jawaban langsung.
```

---

## Mode 1 — Micro Patch

Untuk:

- bug kecil
- edit 1–2 file
- typo UI
- tombol mati
- validasi kecil
- mapping kecil
- fix kecil

Baca hanya:

```text
docs/pipeline/current-state.md
docs/pipeline/timeline.md
docs/critical/audit-gap.md
file target
```

Output wajib:

```text
1. Audit singkat
2. File plan singkat
3. Patch / perubahan
4. Validation
5. Final report
```

Tidak perlu:

- audit penuh
- decision log
- roadmap
- architecture update
- dokumentasi panjang

---

## Mode 2 — Feature Patch

Untuk:

- fitur kecil-menengah
- page/component/module minor
- workflow baru terbatas
- integration ringan
- perubahan beberapa file

Baca:

```text
docs/pipeline/current-state.md
docs/pipeline/timeline.md
docs/critical/audit-gap.md
docs/doc/architecture.md jika relevan
file target
file dependency langsung
```

Output wajib:

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

## Mode 3 — Architecture / Foundation

Untuk:

- project baru
- blueprint
- perubahan besar
- architecture change
- module foundation
- repository structure
- standard/framework update

Baca:

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

Output wajib:

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

## Mode 4 — Review Only

Untuk:

- audit hasil agent
- review patch
- cek gap
- cek risiko
- buat fixing prompt
- tanpa coding

Baca:

```text
current-state
output agent
file yang direview
reference terkait
```

Output wajib:

```text
1. Review summary
2. Gap
3. Risk
4. Validation issue
5. Fixing prompt
```

Dilarang:

```text
coding
rewrite
ubah file
```

---

# MODE DECISION TREE

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

# UNIVERSAL RULE

Agent wajib:

- pilih mode paling ringan
- baca file minimum
- implement sesuai scope
- lakukan validation
- jalankan debug loop jika validation gagal
- update docs sesuai mode
- stop saat objective selesai

Agent dilarang:

- full repo scan
- menambah scope
- membuat opsi berlebihan
- diskusi panjang tanpa output
- rewrite besar tanpa bukti
- bilang selesai tanpa validation

---

# DEBUG LOOP

Jika validation gagal, agent wajib masuk ke DEBUG_LOOP.md.

---

# STOP CONDITION

Berhenti setelah:

```text
Objective selesai
Validation selesai
Docs sesuai mode terupdate
Final report dibuat
```

Jangan lanjut ke task lain.

---

# Status

LOCKED
