# Catat.in

Pencatat pengeluaran pribadi. Offline-first, tanpa akun, data tersimpan di HP.

## Cara 1: Pasang langsung dari Chrome (paling cepat)
1. Upload isi folder `www/` ke hosting statis (Vercel, Netlify, GitHub Pages).
2. Buka alamatnya di Chrome Android.
3. Menu titik tiga, lalu "Instal aplikasi" (atau "Tambahkan ke layar utama").
4. Tekan lama ikon Catat.in di layar utama untuk jalan pintas "Catat pengeluaran".

## Cara 2: Jadi file APK lewat GitHub (tanpa Android Studio)
1. Buat repo GitHub baru, upload semua isi folder ini (termasuk `.github`).
2. Buka tab Actions, pilih "Build APK", tekan "Run workflow".
3. Tunggu sekitar 5 menit, lalu unduh `catatin-apk` dari bagian Artifacts.
4. Ekstrak zip, kirim `app-debug.apk` ke HP, lalu install (izinkan "sumber tidak dikenal").

## Cara 3: Build di laptop
```
npm install
npx cap add android
npx @capacitor/assets generate --android
npx cap sync android
npx cap open android   # Android Studio, lalu Run
```

## Struktur
- `www/index.html`: seluruh app (HTML, CSS, JS)
- `www/sw.js`, `www/manifest.webmanifest`: mode offline dan install PWA
- `capacitor.config.json`, `package.json`, `.github/workflows/build-apk.yml`: pembungkus APK
- `assets/icon-only.png`: sumber ikon app

## Data
Disimpan di localStorage. Fitur Atur, lalu Cadangkan data, menyimpan file JSON untuk pindah HP.
