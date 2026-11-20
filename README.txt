PintarSD Kelas 1 - PWA

ISI
  index.html    aplikasi (konten + logika)
  styles.css    Tailwind sudah di-build (tanpa CDN)
  fonts/        Nunito lokal
  icons/        ikon 192, 512, maskable, apple-touch
  manifest.json identitas aplikasi
  sw.js         service worker (cache offline)
  _build/       bahan untuk build ulang styles.css

PASANG
  1. Upload SELURUH isi folder ini ke hosting HTTPS (GitHub Pages, Netlify, Cloudflare Pages).
     Service worker tidak jalan lewat file:// atau http:// biasa (kecuali localhost).
  2. Buka sekali dengan internet. Setelah itu bisa dipakai offline.
  3. Android Chrome: menu > Instal aplikasi. iOS Safari: Bagikan > Tambah ke Layar Utama.

RILIS UPDATE
  - Edit index.html, lalu naikkan CACHE_VERSION di sw.js.
  - Kalau menambah class Tailwind baru, build ulang CSS:
      cd _build && npm install && npx tailwindcss -c tailwind.config.js -i input.css -o ../styles.css --minify
    (jalankan dengan index.html ada di folder induk; sesuaikan path content di tailwind.config.js)
