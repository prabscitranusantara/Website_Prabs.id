# Cara Deploy + Setup Admin Panel

## 1. Push ke GitHub
Masukkan semua file di folder ini (`index.html`, `admin.html`, `netlify.toml`, `netlify/`)
ke root repo GitHub kamu, lalu `git add . && git commit -m "add product admin panel" && git push`.

## 2. Connect repo ke Netlify
- Buka https://app.netlify.com → **Add new site → Import an existing project**
- Pilih repo GitHub kamu
- Build command: kosongkan
- Publish directory: `.` (titik, root folder)
- Deploy

## 3. Set password admin (WAJIB sebelum panel bisa dipakai)
- Di dashboard Netlify: **Site configuration → Environment variables → Add a variable**
- Key: `ADMIN_PASSWORD`
- Value: password pilihan kamu (jangan pakai yang gampang ditebak)
- Save, lalu trigger deploy ulang (Deploys → Trigger deploy)

## 4. Pakai admin panel
- Buka `https://situs-kamu.netlify.app/admin.html`
- Masukkan password, drag foto produk, isi caption, klik Upload
- Produk otomatis muncul di halaman utama (`index.html`) di section "Produk Kami"

## Catatan keamanan
- `admin.html` tidak di-index Google (ada tag `noindex`), tapi URL-nya tetap bisa diakses
  siapa pun yang tahu link-nya — keamanan bergantung sepenuhnya pada `ADMIN_PASSWORD`.
- Jangan share link `/admin.html` secara publik.
- Maks ukuran file 5MB per gambar, format JPEG/PNG/WEBP/GIF.
