# UMKM Sales Management System

UMKM Sales Management System adalah aplikasi web berbasis Laravel untuk membantu pelaku UMKM mengelola produk, kategori, pelanggan, transaksi penjualan, stok, invoice, dan laporan penjualan dalam satu sistem sederhana.

Aplikasi ini dikembangkan sebagai sistem manajemen penjualan yang ringan, mudah digunakan, dan cocok untuk kebutuhan pencatatan operasional UMKM sehari-hari.

---

## Fitur Utama

### 1. Authentication
- Login pengguna.
- Registrasi akun.
- Edit profil pengguna.
- Update password.
- Logout.

### 2. Dashboard
Dashboard menampilkan ringkasan kondisi usaha, seperti:
- Total produk.
- Total pelanggan.
- Total penjualan hari ini.
- Total penjualan bulan ini.
- Produk dengan stok rendah.
- Top 5 produk terlaris.
- Grafik penjualan 7 hari terakhir.

### 3. Manajemen Kategori
Fitur kategori digunakan untuk mengelompokkan produk agar data lebih rapi.

Fitur yang tersedia:
- Menampilkan daftar kategori.
- Menambah kategori.
- Mengedit kategori.
- Menghapus kategori.
- Menampilkan jumlah produk pada setiap kategori.

### 4. Manajemen Produk
Fitur produk digunakan untuk mengelola data barang yang dijual oleh UMKM.

Fitur yang tersedia:
- Menampilkan daftar produk.
- Menambah produk baru.
- Mengedit data produk.
- Menghapus produk.
- Upload gambar produk.
- Mengatur kode produk.
- Mengatur harga produk.
- Mengatur stok produk.
- Menghubungkan produk dengan kategori.
- Pencarian produk untuk kebutuhan transaksi POS.

### 5. Manajemen Pelanggan
Fitur pelanggan digunakan untuk menyimpan data pembeli atau pelanggan tetap.

Fitur yang tersedia:
- Menampilkan daftar pelanggan.
- Menambah pelanggan.
- Mengedit data pelanggan.
- Menghapus pelanggan.
- Menampilkan total transaksi pelanggan.
- Menampilkan total belanja pelanggan.

### 6. Transaksi Penjualan / POS
Fitur POS digunakan untuk mencatat transaksi penjualan secara langsung.

Fitur yang tersedia:
- Pencarian produk secara cepat.
- Menambahkan produk ke keranjang transaksi.
- Mengatur jumlah produk yang dibeli.
- Menghitung subtotal transaksi.
- Menghitung diskon.
- Menghitung pajak.
- Menghitung total pembayaran.
- Menghitung uang bayar dan kembalian.
- Membuat nomor invoice otomatis.
- Mengurangi stok produk setelah transaksi berhasil.
- Menyimpan detail item penjualan.

### 7. Riwayat dan Detail Penjualan
Fitur ini digunakan untuk melihat transaksi yang sudah terjadi.

Fitur yang tersedia:
- Menampilkan daftar transaksi berdasarkan rentang tanggal.
- Melihat detail transaksi.
- Menampilkan data pelanggan pada transaksi.
- Menampilkan data kasir/user.
- Menampilkan detail item yang dibeli.
- Tampilan invoice/struk transaksi.

### 8. Laporan Penjualan
Fitur laporan digunakan untuk membantu pemilik UMKM menganalisis performa penjualan.

Laporan yang tersedia:
- Total penjualan berdasarkan rentang tanggal.
- Total transaksi.
- Rata-rata nilai transaksi.
- Total produk terjual.
- Tren penjualan harian.
- Penjualan berdasarkan kategori.
- Top 5 produk terlaris.
- Top 5 pelanggan.
- Analisis jam transaksi paling ramai.

> Catatan: menu export PDF dan Excel sudah disiapkan pada route/controller, tetapi masih berupa placeholder dan dapat dikembangkan lebih lanjut.

---

## Teknologi yang Digunakan

- PHP 8.2+
- Laravel 12
- Laravel Breeze
- MySQL
- Blade Template
- Bootstrap 5
- Bootstrap Icons
- Chart.js
- Vite
- NPM
- Composer

---

## Struktur Folder Penting

```text
umkm-sales/
├── app/
│   └── Http/
│       └── Controllers/
│           ├── DashboardController.php
│           ├── ProductController.php
│           ├── CategoryController.php
│           ├── CustomerController.php
│           ├── SaleController.php
│           └── ReportController.php
├── database/
│   ├── migrations/
│   └── seeders/
├── resources/
│   └── views/
│       ├── auth/
│       ├── categories/
│       ├── customers/
│       ├── products/
│       ├── reports/
│       ├── sales/
│       ├── dashboard.blade.php
│       └── welcome.blade.php
├── routes/
│   ├── web.php
│   └── auth.php
├── public/
└── README.md
```

---

## Kebutuhan Sistem

Pastikan perangkat sudah memiliki:

- PHP minimal versi 8.2
- Composer
- Node.js dan NPM
- MySQL / MariaDB
- Web browser
- Git

---

## Cara Instalasi Project

### 1. Clone Repository

```bash
git clone https://github.com/1aghismuhammad/UMKM-SALES.git
cd UMKM-SALES
```

### 2. Install Dependency Laravel

```bash
composer install
```

### 3. Install Dependency Frontend

```bash
npm install
```

### 4. Salin File Environment

```bash
cp .env.example .env
```

Untuk pengguna Windows Git Bash, perintah di atas bisa digunakan. Jika menggunakan Command Prompt, bisa gunakan:

```bash
copy .env.example .env
```

### 5. Generate Application Key

```bash
php artisan key:generate
```

### 6. Konfigurasi Database

Buka file `.env`, lalu sesuaikan konfigurasi database:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=umkm_sales
DB_USERNAME=root
DB_PASSWORD=
```

Buat database baru di MySQL/phpMyAdmin dengan nama:

```text
umkm_sales
```

### 7. Jalankan Migrasi Database

```bash
php artisan migrate
```

Jika project menggunakan file SQL tambahan untuk tabel utama aplikasi, import file SQL tersebut ke database `umkm_sales` melalui phpMyAdmin atau terminal MySQL.

Tabel utama yang digunakan aplikasi:

- users
- categories
- products
- customers
- sales
- sale_items

### 8. Buat Storage Link

```bash
php artisan storage:link
```

Perintah ini dibutuhkan agar gambar produk yang di-upload dapat diakses dari folder `public/storage`.

### 9. Jalankan Frontend Build

Untuk development:

```bash
npm run dev
```

Untuk production build:

```bash
npm run build
```

### 10. Jalankan Server Laravel

```bash
php artisan serve
```

Aplikasi dapat diakses melalui:

```text
http://127.0.0.1:8000
```

---

## Alur Penggunaan Aplikasi

1. Buka halaman utama aplikasi.
2. Login atau register akun.
3. Masuk ke dashboard.
4. Tambahkan kategori produk.
5. Tambahkan produk beserta stok dan harga.
6. Tambahkan data pelanggan jika diperlukan.
7. Buka menu transaksi penjualan.
8. Pilih produk yang dibeli pelanggan.
9. Input jumlah, diskon, pajak, dan pembayaran.
10. Simpan transaksi.
11. Lihat invoice/struk transaksi.
12. Pantau laporan penjualan melalui menu laporan.

---

## Route Utama

| Method | URL | Keterangan |
|---|---|---|
| GET | `/` | Landing page |
| GET | `/dashboard` | Dashboard utama |
| GET | `/products` | Daftar produk |
| GET | `/products/create` | Form tambah produk |
| GET | `/products/search` | Pencarian produk untuk POS |
| GET | `/categories` | Daftar kategori |
| GET | `/customers` | Daftar pelanggan |
| GET | `/sales` | Riwayat penjualan |
| GET | `/sales/create` | Halaman POS/transaksi |
| GET | `/sales/{id}` | Detail transaksi |
| GET | `/reports` | Laporan penjualan |
| GET | `/reports/export-pdf` | Placeholder export PDF |
| GET | `/reports/export-excel` | Placeholder export Excel |

---

## Catatan Pengembangan

Beberapa bagian yang masih dapat dikembangkan lebih lanjut:

- Export laporan ke PDF.
- Export laporan ke Excel.
- Role pengguna, misalnya admin dan kasir.
- Validasi stok agar transaksi tidak bisa melebihi stok tersedia.
- Fitur retur barang.
- Fitur supplier.
- Fitur pembelian/restock barang.
- Riwayat perubahan stok.
- Filter produk berdasarkan kategori.
- Deployment ke hosting/VPS.

---

## Perintah Git Setelah Update README

Setelah mengganti isi `README.md`, jalankan:

```bash
git add README.md
git commit -m "update README project"
git push origin main
```

Jika remote masih mengarah ke repository lama, ubah dulu dengan:

```bash
git remote set-url origin https://github.com/1aghismuhammad/UMKM-SALES.git
git push -u origin main
```

---

## Developer

Project ini dikembangkan sebagai aplikasi manajemen penjualan sederhana untuk UMKM berbasis Laravel.

