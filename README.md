# Prompt-to-SDLC Studio — IBM Bob Capstone

Satu prompt jadi paket SDLC lengkap. Agent IBM Bob terima 1 kalimat ide → keluarkan `index.html + style.css` siap buka, siap print, siap submit. HTML+CSS murni, tanpa JS, tanpa framework, tanpa gambar luar.

Ide default: `Aplikasi bank sampah RW dengan poin QR untuk warga dan rekap otomatis untuk pengurus.`

## Fitur

- 6 tab CSS-only (radio): PRD, Arsitektur, User Stories, API & Data, TODO + Workflow, Test & Risiko.
- 9 section wajib: hero + ide echo verbatim, PRD, diagram box CSS + tabel komponen, 5 user stories, 3 endpoint + 1 skema, TODO 10 checkbox + progress bar counter + timeline 5 tahap, 5 test + 3 risiko, footer.
- TODO interaktif murni CSS (`:checked`, `counter()`, `body:has()`).
- Print-friendly (`@media print`: nav hidden, semua panel tampil).
- Tolak scope-creep: tanpa backend/auth tambahan.

## Rencana pengembangan

### Fase 0 — Capstone (selesai, dokumen)
- [x] PRD, arsitektur, prompt 3-layer, playbook, check.py
- [ ] Generate Bob → `index.html` + `style.css` → verifikasi → screenshot → submit form sebelum 4 Okt 2026

### Fase 1 — Kualitas dokumen (Hackathon prep)
- Template JSON section (`data/sdlc-template.json`) agar 9 section konsisten antar ide.
- Rubrik Mode Kelas: kelengkapan 40 / konsistensi 30 / keterbacaan 20 / kode 10.
- Test ide kedua (regenerasi penuh, pastikan tidak ada sisa ide lama).

### Fase 2 — Integrasi ringan (tanpa cemari core no-JS)
- Log ide ke Google Sheets via GAS `doPost` (nama, ide, tanggal).
- RAG Langflow + AstraDB: PRD lama jadi referensi gaya + auto-suggest user story.
- `enhance.js` opsional pasca-lomba: tombol print/export + save `localStorage`. Core tetap no-JS.

### Fase 3 — Skala Hackathon Nasional (tema Productivity & Smart Business)
- Multi-proyek: 1 HTML kelola N ide via tab tambahan (tetap CSS-only) atau split file per proyek.
- Export PDF 1-klik + cover tim (butuh JS, hanya pasca-lomba).
- Validasi juri: checklist kelayakan 5 menit + skor otomatis dari TODO/test coverage.

### Out of scope (sengaja tidak dibuat)
Backend nyata, auth, DB permanen, multiplayer realtime.