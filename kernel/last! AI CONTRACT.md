# AI CONTRACT

Version : 1.7.0  
Status  : LOCKED  
Owner   : TSA Framework  

---

# AGREEMENT 47 — SINGLE SOURCE OF KNOWLEDGE

## Rule

Setiap jenis informasi hanya boleh memiliki satu sumber resmi.

AI dilarang menduplikasi informasi yang sama ke banyak dokumen tanpa alasan yang jelas.

---

## Objective

Menjaga konsistensi informasi, menghindari konflik dokumentasi, dan mengurangi maintenance yang tidak perlu.

---

## AI Behavior

AI wajib menentukan lokasi resmi untuk setiap jenis informasi.

Contoh:

```text
Architecture     → architecture.md
Roadmap          → roadmap.md
Current State    → current-state.md
Timeline         → timeline.md
Decision         → decision-log.md
Bug History      → bug-history.md
Prompt Library   → prompt-library.md
Debug Loop       → runtime/DEBUG_LOOP.md
```

Dokumen lain hanya boleh memberi referensi, bukan menyalin ulang isi.

---

## Failure Condition

Satu informasi memiliki beberapa versi yang berbeda.

---

## Decision

One Information. One Official Location.

Status:

LOCKED

---

# AGREEMENT 48 — SINGLE RESPONSIBILITY DOCUMENT

## Rule

Setiap dokumen hanya memiliki satu tujuan utama.

Satu dokumen tidak boleh merangkap banyak fungsi.

---

## Objective

Membuat dokumentasi mudah dipahami, dicari, dan dipelihara.

---

## AI Behavior

Contoh:

```text
README.md       → Project introduction
roadmap.md      → Roadmap
architecture.md → Architecture
decision-log.md → Decision
bug-history.md  → Bug history
timeline.md     → Timeline
debug-log.md    → Debug history
```

Jangan mencampur seluruh informasi ke satu file.

---

## Failure Condition

Dokumentasi menjadi panjang, sulit dicari, dan saling tumpang tindih.

---

## Decision

One Document. One Responsibility.

Status:

LOCKED

---

# AGREEMENT 49 — PROJECT BEFORE PERSONAL PREFERENCE

## Rule

Keputusan engineering harus mengikuti kebutuhan Project, bukan preferensi pribadi AI maupun engineer.

---

## Objective

Menjaga konsistensi implementasi dan menghindari perubahan karena selera teknis.

---

## AI Behavior

Jika pattern existing masih valid, ikuti.

Jangan mengganti karena:

- framework favorit
- style favorit
- naming favorit
- pola favorit
- library favorit

Perubahan hanya boleh dilakukan jika ada bug, requirement baru, keputusan resmi Project, atau bukti teknis yang kuat.

---

## Failure Condition

Repository kehilangan konsistensi karena preferensi individu.

---

## Decision

Project Standard Always Wins. Personal Preference Never Leads.

Status:

LOCKED

---

# AGREEMENT 50 — LONG-TERM MAINTAINABILITY

## Rule

Setiap keputusan engineering harus mempertimbangkan kemudahan pemeliharaan jangka panjang.

AI tidak boleh hanya mengejar penyelesaian jangka pendek.

---

## Objective

Membangun Project yang tetap mudah dipahami, dikembangkan, dan dipelihara dalam jangka panjang.

---

## AI Behavior

Sebelum implementasi AI wajib bertanya:

Apakah keputusan ini masih mudah dipahami:

- enam bulan lagi?
- satu tahun lagi?
- dua tahun lagi?

Jika jawabannya tidak, pilih solusi yang lebih sederhana dan stabil.

---

## Failure Condition

Repository hanya dapat dipahami oleh pembuat awalnya.

---

## Decision

Maintainability Is The Greatest Investment.

Status:

LOCKED

---

# DEBUG LOOP REFERENCE

Detailed debug execution follows:

```text
runtime/DEBUG_LOOP.md
```

Status:

LOCKED
