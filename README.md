# Surat Taman — template ucapan interaktif

Satu halaman web (`index.html`, vanilla JS + three.js) berisi perjalanan sinematik di sebuah taman.
Pesan-pesan muncul satu per satu saat kamera berjalan, lalu di akhir ada kursi dengan tiga benda
yang bisa diketuk: **postcard** (balik ke foto), **bunga** (mekar, kelopak jatuh), dan **surat** (dua halaman).

## Cara memakai sebagai template

Buka `index.html`, cari blok `const CONFIG = { ... }` di awal `<script>` pertama. Semua isi ada di situ:

| Kunci | Fungsi |
|---|---|
| `title` | judul tab browser |
| `intro` | teks di layar pembuka (sebelum tombol "mulai") |
| `messages` | pesan selama berjalan; `\n` = pindah baris; yang terakhir tampil sebelum kursi |
| `postcard` | tiga baris di postcard (`line1..3`) dan tanggal di cap pos (`date`) |
| `photo` | foto di balik postcard (ganti `assets/pic.jpg` atau ubah path) |
| `letter` | daftar halaman surat; tiap halaman berisi daftar paragraf |
| `youtube` | ID video YouTube untuk musik (kosongkan = tanpa musik) |

Pengaturan lain (tempo animasi, kecepatan kamera, ukuran benda) ada sebagai variabel CSS di `:root`
dan konstanta `MAX_SPEED` — lihat komentar di kodenya.

## Menjalankan

```bash
python -m http.server 8000
```

Buka `http://localhost:8000`. Butuh internet (three.js, font Google, dan pemutar YouTube dimuat dari CDN).

## Deploy

Unggah **seluruh folder** (`index.html` + `assets/`) ke hosting statis (Netlify Drop, GitHub Pages, dll).
Mengunggah `index.html` saja akan membuat gambar tidak termuat.

## Aset

Gambar di `assets/` adalah aset pemilik repo. Pastikan kamu punya hak memakainya sebelum
mempublikasikan repo ini, atau ganti dengan gambar milikmu sendiri (nama file tetap sama).
