# expect-prompt-cutting-export.md

Status : EXAMPLE  
Source : moved from `expect prompt!.md`  
Note   : This file is project-specific example, not global TSA contract.

---

ROLE

Anda adalah Senior Frontend Engineer untuk project Cutting AMT.

OBJECTIVE

Tambahkan fitur Export Excel pada halaman:

#/layering-material

Tombol Export Excel diletakkan di area kosong antara End Date dan tombol View/Loading.

==================================================
SCOPE
==================================================

Frontend only.

JANGAN audit seluruh repo.
JANGAN ubah backend.
JANGAN ubah API.
JANGAN ubah scanner barcode.
JANGAN ubah behavior View.
JANGAN ubah datatable existing.
JANGAN ubah layout besar.
JANGAN tambah library baru.

==================================================
READ ONLY
==================================================

Baca hanya:

frontend/src/pages/LayeringMaterial.jsx
frontend/src/services/layeringMaterialService.js
frontend/src/styles.css
frontend/package.json

==================================================
MODIFY ONLY
==================================================

Boleh ubah:

frontend/src/pages/LayeringMaterial.jsx
frontend/src/styles.css

Boleh buat file baru:

frontend/src/utils/layeringMaterialExportMapper.js
frontend/src/utils/exportLayeringMaterialExcel.js

JANGAN ubah file lain.

==================================================
KEEP
==================================================

Pertahankan:

- Scan SPK Barcode area
- input PO No
- input Component
- Start Date
- End Date
- tombol View / Loading
- behavior loading
- table existing
- pagination existing jika ada
- style existing
- service existing

==================================================
CHANGE
==================================================

Tambahkan tombol:

Export Excel

Lokasi:

PO No | Component | Start Date | End Date | Export Excel | View

Gunakan style button yang konsisten dengan FE existing.

==================================================
DATA SOURCE
==================================================

Export Excel menggunakan data datatable Layering Material yang sudah ada di state frontend.

JANGAN request ulang API.
JANGAN buat endpoint export.
JANGAN mengubah service fetch.

Jika datatable hanya berisi current page, export current page saja.

==================================================
EXCEL CONTENT
==================================================

Kolom Excel mengikuti kolom datatable Layering Material yang sedang ada.

JANGAN export kolom Action.

Jika field row memakai camelCase atau snake_case, mapper harus handle fallback.

==================================================
CREATE FILE 1
==================================================

frontend/src/utils/layeringMaterialExportMapper.js

Buat function:

export const mapLayeringMaterialRowsForExcel = (rows = []) => {
  return rows.map((row, index) => ({
    No: index + 1,
    'PO No': row.poNo ?? row.po_no ?? row.po ?? '',
    Component: row.componentName ?? row.component_name ?? row.component ?? '',
    'Component Code': row.componentCode ?? row.component_code ?? '',
    'Material Code': row.materialCode ?? row.material_code ?? '',
    'Material Name': row.materialName ?? row.material_name ?? '',
    Size: row.size ?? '',
    QTY: row.qty ?? row.quantity ?? row.qtyUsage ?? row.qty_usage ?? '',
    Unit: row.unit ?? row.uom ?? '',
    Date: row.date ?? row.usageDate ?? row.usage_date ?? row.createdAt ?? row.created_at ?? '',
  }));
};

Sesuaikan nama kolom dengan field datatable existing di LayeringMaterial.jsx.
Jangan ubah bentuk row existing.

==================================================
CREATE FILE 2
==================================================

frontend/src/utils/exportLayeringMaterialExcel.js

Gunakan library Excel yang sudah ada di package.json.

Jika ada exceljs, gunakan exceljs.
Jika ada xlsx, gunakan xlsx.
Jangan install library baru.

Function:

exportLayeringMaterialExcel(exportRows)

Output file:

Layering_Material_YYYY-MM-DD.xlsx

Worksheet:

Layering Material

Style sederhana:
- header bold
- freeze header jika mudah
- width kolom auto sederhana

==================================================
PAGE CHANGE
==================================================

Di:

frontend/src/pages/LayeringMaterial.jsx

Tambahkan import mapper dan exporter.

Tambahkan handler:

handleExportExcel()

Flow:

1. Ambil rows datatable existing.
2. Jika rows kosong:
   alert("Tidak ada data untuk diexport.")
3. Map rows dengan mapLayeringMaterialRowsForExcel.
4. Export dengan exportLayeringMaterialExcel.

Jangan ubah handle View.
Jangan ubah scanner.
Jangan ubah fetch.
Jangan ubah filter.

==================================================
VALIDATION
==================================================

Jalankan:

cd frontend
npm run build

Manual check:

1. Buka #/layering-material.
2. Tombol Export Excel muncul di antara End Date dan View.
3. Scanner tetap normal.
4. View tetap normal.
5. Datatable tetap normal.
6. Klik Export Excel saat data ada menghasilkan .xlsx.
7. Kolom Action tidak ikut export.
8. Klik Export Excel saat data kosong menampilkan alert.

==================================================
STOP CONDITION
==================================================

Berhenti setelah:

- tombol Export Excel muncul
- export memakai data datatable existing
- file .xlsx berhasil dibuat
- build selesai
- tidak ada file di luar scope yang berubah