# BOOT.md

Status  : LOCKED  
Version : 1.7.0  
Purpose : Menyiapkan konteks minimum berdasarkan Runtime Mode  

---

# Boot Flow

```text
Receive Task
↓
Read MODE_SELECTOR.md
↓
Select Runtime Mode
↓
Load Minimum Required Context
↓
Start Execution
```

---

# Rule

Do not load more than required by selected mode.

If extra file is needed, write:

```text
NEED_FILE:
path:
reason:
```

---

# Failure

Boot gagal jika:

- mode tidak dipilih
- langsung full repo scan
- membaca file tidak relevan
- implementasi dimulai sebelum context minimum tersedia

---

# Status

LOCKED
