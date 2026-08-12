# Kios Akun — Dispenser Tiket (PWA)

App generator username & password acak bergaya "kios tiket" — bisa di-install jadi aplikasi di HP.

Ini **static site murni** (HTML/CSS/JS biasa) — beda dari project sebelumnya, project ini **gak butuh `npm install` atau proses build sama sekali**. Tinggal upload & deploy apa adanya.

## Deploy ke Vercel lewat GitHub

1. Push semua file di folder ini ke repo GitHub baru (lewat terminal, atau upload manual satu-satu kayak sebelumnya — kali ini lebih gampang karena cuma ada 4 file + 1 folder icon).
2. Buka [vercel.com](https://vercel.com) → **Add New Project** → import repo tadi.
3. Di pengaturan project:
   - Framework Preset: **Other**
   - Build Command: **kosongkan** (biarin kosong, gak perlu build)
   - Output Directory: **kosongkan** / `.`
4. Deploy. Buka URL-nya di HP.

## Cara install di HP

- **Android (Chrome)**: buka situsnya, tunggu sebentar, tap menu titik tiga → **Install app** / **Add to Home screen**.
- **iOS (Safari)**: tap tombol **Share** → **Add to Home Screen** (iOS gak punya tombol install otomatis, ini batasan dari Apple).

## Struktur project

```
index.html       # seluruh app (HTML+CSS+JS jadi satu, sesuai file asli)
manifest.json     # metadata PWA
sw.js             # service worker (wajib untuk installability)
icons/            # logo app (tema tiket + stempel) di berbagai ukuran
vercel.json       # header cache untuk sw.js & manifest.json
```

## Catatan soal data

Sama seperti project sebelumnya: kalau dibuka di Claude (preview), data kesimpen ke penyimpanan akun Claude. Begitu di-deploy sendiri ke Vercel dan diakses langsung dari HP, app ini otomatis pindah pakai `localStorage` biasa — jadi datanya nempel di HP/browser itu doang, gak sinkron ke device lain kecuali kamu pakai fitur **Backup Data** (.json) di dalam app buat pindahin manual.
