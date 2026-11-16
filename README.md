# Landing Page Tukang Paip (Plumber)

Landing page satu halaman untuk jasa tukang paip dan ubah suai panggilan, dalam Bahasa Malaysia. Dibuat dengan HTML, CSS, dan JavaScript biasa, tanpa framework dan tanpa proses build. Cukup buka file HTML di browser.

## Fitur

- Desain modern dan responsif (desktop, tablet, HP)
- Hero dua kolom di desktop (gambar di kiri, tulisan di kanan), dan satu kolom di HP
- Mode terang dan gelap, dengan tombol ganti tema dan pilihan tersimpan di browser
- Navigasi menempel di atas dan tombol WhatsApp mengambang
- Animasi muncul saat scroll dan angka statistik yang menghitung naik (otomatis dinonaktifkan untuk pengguna yang memilih `prefers-reduced-motion`)
- Tombol telefon dan WhatsApp terhubung ke satu pengaturan pusat

## Struktur halaman

1. Navigasi dan hero (judul, tombol WhatsApp, poin keunggulan, gambar maskot)
2. Statistik singkat
3. Perkhidmatan Kami (kartu dengan foto)
4. Kenapa Pilih Kami
5. Cara Kerja (3 langkah)
6. Kawasan Perkhidmatan dan jaminan
7. Aktiviti Kerja Kami (galeri)
8. Soalan Lazim (FAQ)
9. Ajakan bertindak (CTA) dan footer

## Menjalankan

Tidak perlu instalasi apa pun.

1. Simpan file `landing-page-tukang-paip.html` (dan folder foto jika ada) dalam satu folder.
2. Klik dua kali file HTML untuk membukanya di browser.

Font (Plus Jakarta Sans) dimuat dari Google Fonts, jadi butuh koneksi internet. Tanpa internet, halaman tetap tampil dengan font bawaan sistem.

## Mengubah nama, nomor, dan pesan WhatsApp

Semua pengaturan ada di blok `CONFIG` di bagian `<script>` paling bawah file HTML:

```js
const CONFIG = {
  brand: "Nama Bisnis Anda",
  phoneDisplay: "01x-xxx xxxx",       // tampilan nomor di halaman
  phoneTel: "+60100000000",           // format antarabangsa untuk butang telefon
  waNumber: "60100000000",            // tanpa tanda +
  waMessage: "Hai, saya ada masalah paip. Boleh bantu saya?"
};
```

Satu perubahan di sini otomatis berlaku di seluruh halaman: navigasi, hero, tombol CTA, footer, dan tombol WhatsApp mengambang.

## Mengganti foto layanan

Kartu di bagian Perkhidmatan Kami memakai tag gambar seperti ini:

```html
<img src="foto/sinki-tersumbat.jpg" alt="Sinki tersumbat" loading="lazy" onerror="this.remove()">
```

Ada dua cara memasang foto:

- **Pakai folder:** taruh foto di folder yang sama dengan file HTML dan sesuaikan nilai `src` (misalnya `foto/` atau `Asset/`). Ekstensi harus cocok dengan nama file, misalnya `.jpg` atau `.jpeg`.
- **Ganti langsung:** ubah `src` ke nama file foto Anda.

Nama file bawaan:

| Layanan | File |
| --- | --- |
| Sinki / Saluran Tersumbat | `sinki-tersumbat.jpg` |
| Tandas Tersumbat | `tandas-tersumbat.jpg` |
| Paip Bocor | `paip-bocor.jpg` |
| Pemasangan Paip | `pemasangan-paip.jpg` |
| Pasang Water Heater | `water-heater.jpg` |
| Jubin & Ubah Suai | `jubin-ubah-suai.jpg` |

Kalau sebuah foto belum ada, kartu menampilkan kotak placeholder "Letak foto di sini". Foto ditampilkan utuh (tidak dipotong) dengan latar kabur dari foto itu sendiri, jadi foto potret maupun lanskap tetap rapi.

## Mengganti gambar hero

Gambar maskot di hero tertanam langsung di HTML sebagai data base64 pada tag `<img class="mascot" ...>`. Untuk menggantinya:

- Ubah nilai `src` menjadi path file gambar biasa, misalnya `src="foto/hero.jpg"`, atau
- Konversi gambar ke base64 jika Anda ingin tetap satu file.

Gunakan gambar yang memang Anda punya hak pakainya.

## Mengubah teks dan isi lain

Semua teks ada langsung di HTML, jadi bisa diubah dengan editor teks biasa:

- **Statistik:** ubah `data-count` (angka) dan `data-suffix` (akhiran) pada elemen `.stat`.
- **Kawasan:** ubah elemen `.chip` di bagian Kawasan Perkhidmatan dan teks kawasan di footer.
- **Galeri:** kotak berwarna di bagian Aktiviti Kerja Kami hanyalah placeholder. Ganti dengan tag `<img>` berisi foto kerja asli.
- **FAQ:** tambah atau ubah blok `<details>`.
- **Warna:** ubah variabel di `:root` (misalnya `--primary`, `--primary-2`, `--accent`) pada bagian awal `<style>`.

## Menayangkan ke internet

Karena hanya file statis, halaman ini bisa dipasang di hosting statis mana pun, misalnya GitHub Pages, Netlify, Cloudflare Pages, atau hosting biasa. Unggah file HTML bersama folder foto, lalu ganti nama file HTML menjadi `index.html` agar terbuka otomatis di alamat utama.

## Catatan sebelum tayang

- Periksa ulang nama bisnis, nomor telefon, nomor WhatsApp, dan teks (termasuk ejaan di judul dan deskripsi).
- Angka statistik dan masa jaminan di halaman adalah contoh. Isi sesuai kondisi bisnis Anda yang sebenarnya.
- Pastikan foto, gambar, dan testimoni yang dipakai milik Anda atau berlisensi untuk digunakan.
- Uji tampilan di HP sungguhan dan coba tombol telefon serta WhatsApp.

## Struktur file yang disarankan

```
.
├── index.html        (atau landing-page-tukang-paip.html)
├── README.md
└── foto/
    ├── sinki-tersumbat.jpg
    ├── tandas-tersumbat.jpg
    ├── paip-bocor.jpg
    ├── pemasangan-paip.jpg
    ├── water-heater.jpg
    └── jubin-ubah-suai.jpg
```