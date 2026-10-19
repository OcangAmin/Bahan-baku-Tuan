# Daily Stock & Order Bahan Baku

Aplikasi web satu halaman untuk mencatat stok harian 67 bahan baku dan mengirim order lewat WhatsApp.

**Buka aplikasi:** https://ocangamin.github.io/Bahan-baku-Tuan/

## Cara pakai harian

1. **Stok** – isi stok **Bar** dan **Gudang** tiap bahan. Isi **Min** (stok minimum) sekali saja; nilainya tetap tersimpan untuk hari berikutnya.
2. Bahan yang total stoknya di bawah Min ditandai **Kurang** beserta saran jumlah order (Min − (Bar + Gudang)).
3. **Order** – tekan **Tambah yang kurang** untuk memasukkan semua bahan yang kurang sesuai saran, atau tambah bahan satu per satu. Ubah jumlah bila perlu.
4. **Kirim** – periksa pratinjau pesan, lalu tekan **Buka WhatsApp** dan **Kirim** di WhatsApp. Unduh CSV order atau CSV stok bila perlu arsip.
5. Besok paginya tekan **Mulai hari baru**: hitungan dan order dikosongkan, sedangkan Min, satuan, nomor WhatsApp, dan format CSV tetap.

## Pengaturan

Diatur di tab **Kirim** dan tersimpan di perangkat masing-masing:

- **Nomor WhatsApp tujuan** – tekan *Ubah nomor*. Nomor default ada di `DEFAULT_WA` pada `index.html`.
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

## Deploy

Halaman di-hosting di GitHub Pages dari branch `main`. Setiap perubahan yang di-merge ke `main` tampil sekitar satu menit kemudian. Tidak ada proses build: buka `index.html` langsung di browser untuk mencoba perubahan.
