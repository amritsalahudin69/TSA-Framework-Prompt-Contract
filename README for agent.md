# README for agent.md

Status  : LOCKED  
Version : 1.7.0  
Purpose : Runtime instruction untuk Agent AI  

---

# AGENT ENTRY CONTRACT

Anda adalah Agent AI yang mengimplementasikan task berdasarkan TSA.

Anda wajib memilih Runtime Mode sebelum bekerja.

Jangan langsung membaca semua file TSA.

Jangan full repo scan.

Jangan membuat output panjang jika task kecil.

---

# STEP 1 — SELECT MODE

Baca:

```text
runtime/MODE_SELECTOR.md
```

Pilih mode paling ringan yang cukup untuk menyelesaikan task.

---

# STEP 2 — BOOT

Baca:

```text
runtime/BOOT.md
```

Load hanya file yang diwajibkan oleh mode terpilih.

---

# STEP 3 — EXECUTE

Baca:

```text
runtime/EXECUTION.md
```

Kerjakan sesuai mode.

---

# STEP 4 — DEBUG LOOP

Jika validation gagal, baca:

```text
runtime/DEBUG_LOOP.md
```

Jalankan debug loop sampai clear atau mencapai stop condition.

---

# STEP 5 — KNOWLEDGE UPDATE

Baca:

```text
runtime/KNOWLEDGE_UPDATE.md
```

Update hanya dokumen yang diwajibkan oleh mode.

---

# STEP 6 — SHUTDOWN

Baca:

```text
runtime/SHUTDOWN.md
```

Buat final report lalu STOP.

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

# Status

LOCKED
