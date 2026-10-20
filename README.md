# Daily Stock & Order Bahan Baku

Aplikasi web satu halaman untuk mencatat stok harian 67 bahan baku dan mengirim order lewat WhatsApp.

**Buka aplikasi:** https://ocangamin.github.io/Bahan-baku-Tuan/

## Cara pakai harian

Halaman terdiri dari tiga langkah. Pindah langkah lewat daftar langkah di atas atau tombol di bar bawah; tombol Back di browser juga bisa dipakai.

1. **Hitung stok** – isi stok **Bar** dan **Gudang** tiap bahan. Isi **Min** (stok minimum) sekali saja; nilainya tetap tersimpan untuk hari berikutnya. Bahan yang total stoknya di bawah Min ditandai **Kurang** beserta saran jumlah order (Min − (Bar + Gudang)). Tekan `/` untuk langsung mencari bahan.
2. **Susun order** – tekan **Tambah yang kurang** untuk memasukkan semua bahan yang kurang sesuai saran, atau tambah bahan satu per satu. Ubah jumlah bila perlu. Baris tanpa jumlah tidak ikut dikirim.
3. **Kirim order** – isi PIC (diingat untuk hari berikutnya), periksa pratinjau pesan, lalu tekan **Kirim lewat WhatsApp** dan **Kirim** di WhatsApp. Unduh CSV order atau CSV stok bila perlu arsip.

Besok paginya tekan **Mulai hari baru**: hitungan dan order dikosongkan setelah konfirmasi, sedangkan Min, satuan, PIC, nomor WhatsApp, dan format CSV tetap.

## Pengaturan

Diatur di langkah **Kirim order** dan tersimpan di perangkat masing-masing:

- **Nomor WhatsApp tujuan** – ketuk nomornya untuk mengubah; Enter menyimpan, Esc membatalkan. Nomor default ada di `DEFAULT_WA` pada `index.html`.
- **Format CSV** – *Standar* (pemisah koma, untuk Google Sheets atau Excel berbahasa Inggris) atau *Excel Indonesia* (pemisah titik koma, desimal koma).

## Data tersimpan di mana

Semua isian disimpan otomatis di browser perangkat yang dipakai (`localStorage`), jadi tidak hilang saat halaman di-refresh atau ditutup. Data **tidak** dibagi antar-perangkat atau antar-staf, dan akan hilang bila data browser dihapus.

## Mengubah daftar bahan

Edit `bahanList` di `index.html`. Setiap bahan berisi:

```js
{no:1, name:"CARAMEL", category:"SYRUP", satuan:"BOTOL"},
```

- `no` harus unik. Jangan ubah `no` bahan yang sudah ada, karena isian yang tersimpan memakai nomor ini.
- `category` salah satu dari `SYRUP`, `POWDER`, `SAUS`, `OTHER`, `BEANS`.
- `satuan` adalah satuan default; staf tetap bisa menggantinya di kolom Satuan.

## Desain

Tampilan mengikuti VectorLab UX skills dengan profil bawaan (gaya Stripe, WCAG AA): pola halaman *Form (wizard)*, tiga ketebalan huruf, teks minimal 12 px, area sentuh minimal 44 × 44 px, konfirmasi bernama untuk setiap aksi hapus, validasi saat kolom ditinggalkan, dan tanpa scroll horizontal di lebar 375 px.

## Deploy

Halaman di-hosting di GitHub Pages dari branch `main`. Setiap perubahan yang di-merge ke `main` tampil sekitar satu menit kemudian. Tidak ada proses build: buka `index.html` langsung di browser untuk mencoba perubahan.
