# Daily Stock & Order Bahan Baku

Aplikasi web satu halaman untuk mencatat stok harian bahan baku dan mengirim order lewat WhatsApp.
Staf membukanya lewat GitHub Pages: https://ocangamin.github.io/Bahan-baku-Tuan/

## File
- `index.html` — seluruh aplikasi: HTML, CSS, dan JS dalam satu file. Tidak ada proses build.
- `README.md` — cara pakai untuk staf. Perbarui bila alur pemakaian berubah.

## Aturan kerja
- **Jangan ubah format data `localStorage` tanpa migrasi.** Semua isian ada di kunci `bahan-baku-tuan:v2` di perangkat
  staf. `loadState()` membaca data lama, termasuk field `tab` dari versi sebelumnya; pertahankan kecocokan itu.
- **Daftar bahan ada di `bahanList`.** `no` harus unik dan tidak boleh diubah untuk bahan yang sudah ada, karena isian
  tersimpan memakai nomor ini. `category` hanya `SYRUP`, `POWDER`, `SAUS`, `OTHER`, atau `BEANS`.
- **Merge ke `main` langsung tayang** sekitar satu menit kemudian, jadi kerjakan di cabang dan tanyakan apakah pengguna
  mau dibuatkan Pull Request.
- Tampilan mengikuti VectorLab UX skills: pola *Form (wizard)*, teks minimal 12 px, area sentuh minimal 44 × 44 px,
  konfirmasi bernama untuk aksi hapus, dan tanpa scroll horizontal di lebar 375 px.
- Uji dengan membuka `index.html` di browser pada ukuran layar HP (390×844) sebelum push.
- Teks yang tampil ke pengguna memakai bahasa Indonesia.
