# 🏪 Aplikasi Manajemen Mini Market Jayusman

![Laravel Version](https://img.shields.io/badge/Laravel-11.x-red?style=for-the-badge&logo=laravel)
![PHP Version](https://img.shields.io/badge/PHP-8.2%2B-blue?style=for-the-badge&logo=php)
![MySQL Version](https://img.shields.io/badge/MySQL-8.0%2B-orange?style=for-the-badge&logo=mysql)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.x-06B6D4?style=for-the-badge&logo=tailwindcss)
![Spatie Permission](https://img.shields.io/badge/Spatie-Permission-9B59B6?style=for-the-badge)
![License](https://img.shields.io/badge/License-Internal%20Use-green?style=for-the-badge)

---

## 📋 DAFTAR ISI

1. [Tentang Aplikasi](#-tentang-aplikasi)
2. [Latar Belakang Masalah](#-latar-belakang-masalah)
3. [Fitur Utama](#-fitur-utama)
4. [Teknologi yang Digunakan](#-teknologi-yang-digunakan)
5. [Persyaratan Sistem](#-persyaratan-sistem)
6. [Instalasi](#-instalasi)
7. [Struktur Database](#-struktur-database)
8. [Akun Uji Coba](#-akun-uji-coba)
9. [Role dan Hak Akses](#-role-dan-hak-akses)
10. [Cara Penggunaan](#-cara-penggunaan)
11. [Troubleshooting](#-troubleshooting)
12. [Lisensi](#-lisensi)

---

## 🏪 Tentang Aplikasi

Aplikasi Manajemen Mini Market Jayusman adalah sistem informasi manajemen terintegrasi yang dirancang khusus untuk membantu **Bapak Jayusman** dalam mengelola **5 cabang mini market** yang tersebar di berbagai kota (Jakarta, Bandung, Surabaya, Semarang, Yogyakarta).

### Visi Aplikasi

Menciptakan sistem manajemen yang transparan, efisien, dan dapat diandalkan untuk mendukung operasional mini market yang tersebar di berbagai lokasi.

### Misi Aplikasi

1. Menyediakan akses monitoring real-time dari mana saja
2. Mencegah potensi kecurangan melalui sistem audit trail
3. Memudahkan pengambilan keputusan berbasis data
4. Meningkatkan efisiensi operasional cabang

---

## 📋 Latar Belakang Masalah

### Permasalahan yang Dihadapi

| No | Masalah | Dampak |
|----|---------|--------|
| 1 | **Harus datang langsung** ke setiap cabang untuk mengecek transaksi dan stok barang | Membuang waktu dan biaya operasional |
| 2 | **Kurangnya pengawasan** terhadap aktivitas transaksi harian | Potensi kecurangan tidak terdeteksi |
| 3 | **Pegawai tidak jujur** memanipulasi transaksi dan stok barang | Kerugian finansial bagi perusahaan |
| 4 | **Keterlambatan informasi** mengenai kondisi stok dan pendapatan | Sulit mengambil keputusan bisnis tepat waktu |
| 5 | **Tidak ada sistem terpusat** untuk memantau semua cabang | Data tersebar dan sulit direkonsiliasi |

### Struktur Organisasi Setiap Cabang

```
                    Bapak Jayusman (Owner)
                            │
                            ▼
              ┌─────────────────────────┐
              │    Manajer Toko (GM)    │
              │  (Bertanggung jawab ke owner)│
              └─────────────────────────┘
                            │
                            ▼
              ┌─────────────────────────┐
              │     Supervisor (SPV)    │
              │   (Mengawasi transaksi) │
              └─────────────────────────┘
                            │
              ┌─────────────┴─────────────┐
              │                           │
              ▼                           ▼
    ┌─────────────────┐         ┌─────────────────┐
    │     Kasir       │         │  Pegawai Gudang │
    │ (Proses transaksi)│       │ (Kelola stok)   │
    └─────────────────┘         └─────────────────┘
```

### Solusi yang Diberikan

Dikembangkan sebuah **aplikasi berbasis web** menggunakan **Laravel 11** dengan **database MySQL** yang memberikan:

| Keunggulan | Deskripsi |
|------------|-----------|
| 🌐 **Akses dari mana saja** | Cukup koneksi internet, Bapak Jayusman bisa memantau semua cabang |
| ⏱️ **Monitoring real-time** | Setiap transaksi dan perubahan stok langsung terlihat |
| 👥 **Sistem Role-Based Access** | Setiap pegawai memiliki akses sesuai jabatan |
| 📊 **Laporan lengkap** | Cetak laporan transaksi dan stok per tanggal |
| 🔒 **Keamanan terjamin** | Audit trail, soft delete, dan authorization |
| 📱 **Responsif** | Bisa diakses dari desktop, tablet, maupun mobile |

---

## ✨ Fitur Utama

### 1. Dashboard Utama

| Komponen | Deskripsi |
|----------|-----------|
| **Filter Cabang** | Khusus Owner, bisa memilih cabang yang ingin dipantau |
| **Statistik Real-time** | Transaksi hari ini, pendapatan, stok menipis, total produk |
| **Trend Analysis** | Perbandingan dengan hari kemarin (naik/turun persentase) |
| **Grafik Pendapatan** | Visualisasi pendapatan 7 hari terakhir |
| **Peringatan Stok** | Alert otomatis jika stok menipis |
| **Transaksi Terbaru** | 10 transaksi terakhir dengan link detail dan print |

### 2. Manajemen Cabang (Owner Only)

| Fitur | Deskripsi |
|-------|-----------|
| **List Cabang** | Tampilan grid card dengan informasi lengkap |
| **Filter & Search** | Filter berdasarkan status dan pencarian nama/kode |
| **Statistik per Cabang** | Jumlah produk, karyawan, transaksi hari ini |
| **Detail Cabang** | Grafik pendapatan 12 bulan, transaksi terbaru, stok menipis |
| **CRUD Cabang** | Tambah, edit, hapus, toggle status aktif |
| **Reset Password Massal** | Reset semua password karyawan di satu cabang |

### 3. Manajemen Produk

| Fitur | Deskripsi |
|-------|-----------|
| **CRUD Produk** | Tambah, edit, hapus, lihat detail produk |
| **Generate Barcode** | Otomatis generate barcode dengan format 899xxxxx |
| **Atur Stok** | Stok masuk, keluar, penyesuaian dengan catatan |
| **Riwayat Stok** | Log lengkap perubahan stok (siapa, kapan, berapa) |
| **Filter Lengkap** | Cabang, kategori, status stok, pencarian |
| **Margin Keuntungan** | Otomatis hitung laba per unit dan persentase |

### 4. Transaksi (Point of Sale)

| Fitur | Deskripsi |
|-------|-----------|
| **Sistem Keranjang** | Seperti POS modern, bisa tambah/hapus item |
| **Barcode Scanner** | Input cepat dengan scanner barcode |
| **Auto Calculation** | Subtotal, pajak 11%, total, kembalian |
| **Catatan Transaksi** | Bisa tambah catatan untuk setiap transaksi |
| **Cetak Struk** | Format struk minimarket, auto print |
| **Pembatalan** | Batalkan transaksi dengan alasan (soft delete) |

### 5. Laporan Lengkap

| Jenis Laporan | Fitur |
|---------------|-------|
| **Laporan Harian** | Summary card, grafik jam sibuk, top 10 produk, detail transaksi |
| **Laporan Bulanan** | Summary card, grafik pendapatan harian, perbandingan cabang |
| **Laporan Stok** | Summary card, distribusi kategori, tabel produk dengan status |
| **Export** | CSV (Excel) dan PDF untuk semua laporan |

### 6. Audit Trail

| Fitur | Deskripsi |
|-------|-----------|
| **Transaksi Dibatalkan** | Lihat semua transaksi yang dibatalkan |
| **Produk Terhapus** | Lihat semua produk yang dihapus (soft delete) |
| **Restore Data** | Kembalikan data yang terhapus |
| **Force Delete** | Hapus permanen data (khusus owner) |
| **Alasan Wajib** | Pembatalan transaksi harus disertai alasan |

### 7. Profil & Keamanan

| Fitur | Deskripsi |
|-------|-----------|
| **Update Profil** | Ubah nama dan email |
| **Update Password** | Ganti password dengan konfirmasi |
| **Toggle Password** | Show/hide password |
| **Informasi Akun** | Role, cabang, tanggal dibuat |
| **Wajib Ganti Password** | Password default harus diganti saat login pertama |

---

## 🛠️ Teknologi yang Digunakan

### Backend

| Teknologi | Versi | Fungsi |
|-----------|-------|--------|
| Laravel | 11.x | Framework utama aplikasi |
| PHP | 8.2+ | Bahasa pemrograman |
| MySQL | 8.0+ | Database |
| Spatie Laravel Permission | 6.x | Manajemen role & permission |

### Frontend

| Teknologi | Versi | Fungsi |
|-----------|-------|--------|
| Blade Template | - | Template engine Laravel |
| TailwindCSS | 3.x | Styling dan UI |
| Font Awesome | 6.5.1 | Icon library |
| Chart.js | 4.x | Grafik dan visualisasi data |
| Alpine.js | 3.x | Interaktivitas ringan |
| SweetAlert2 | 11.x | Notifikasi dan konfirmasi |

### Library Tambahan

| Library | Fungsi |
|---------|--------|
| Laravel Breeze | Authentication scaffolding |
| Laravel Excel | Export data ke Excel/CSV |
| Barryvdh DomPDF | Export data ke PDF |
| Spatie Permission | Role & permission management |

---

## 💻 Persyaratan Sistem

| Komponen | Minimal | Rekomendasi |
|----------|---------|-------------|
| **PHP** | 8.2 | 8.3+ |
| **Composer** | 2.x | 2.5+ |
| **MySQL** | 8.0 | 8.0+ |
| **Node.js** | 18.x | 20.x |
| **NPM** | 9.x | 10.x |
| **Web Server** | Apache/Nginx | Apache/Nginx |

### Ekstensi PHP yang Diperlukan

```bash
- BCMath
- Ctype
- cURL
- DOM
- Fileinfo
- GD
- JSON
- Mbstring
- OpenSSL
- PDO
- Tokenizer
- XML
- Zip
```

---

## 🚀 Instalasi

### Langkah 1: Clone Repository

```bash
git clone https://github.com/yourusername/pak-jayusman-minimarket.git
cd pak-jayusman-minimarket
```

### Langkah 2: Install Dependencies

```bash
# Install PHP dependencies
composer install

# Install Node.js dependencies
npm install
```

### Langkah 3: Konfigurasi Environment

```bash
# Copy environment file
cp .env.example .env

# Generate application key
php artisan key:generate
```

Edit file `.env`:

```env
# Database Configuration
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=minimarket_db
DB_USERNAME=root
DB_PASSWORD=yourpassword

# Application URL
APP_URL=http://localhost:8000
APP_NAME="Minimarket Jayusman"
```

### Langkah 4: Buat Database

```sql
CREATE DATABASE minimarket_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

### Langkah 5: Jalankan Migrasi & Seeder

```bash
# Jalankan migrasi
php artisan migrate

# Jalankan seeder (data awal)
php artisan db:seed
```

**Data yang akan dibuat:**
- 5 cabang (Jakarta, Bandung, Surabaya, Semarang, Yogyakarta)
- Roles: owner, manager, supervisor, cashier, warehouse
- Users: 1 owner, 5 manager, 5 supervisor, 10 cashier, 5 warehouse
- Products: 40 produk (8 produk per cabang)
- Permissions: 20+ permission

### Langkah 6: Build Assets

```bash
npm run build
```

### Langkah 7: Jalankan Server

```bash
# Terminal 1: Laravel Development Server
php artisan serve

# Terminal 2: Vite Development Server (opsional, untuk development)
npm run dev
```

### Langkah 8: Akses Aplikasi

Buka browser dan akses: **http://localhost:8000**

---

## 📊 Struktur Database

### Entity Relationship Diagram (ERD)

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   branches  │     │    users    │     │  products   │
├─────────────┤     ├─────────────┤     ├─────────────┤
│ id (PK)     │────<│ branch_id   │     │ id (PK)     │
│ code        │     │ id (PK)     │     │ branch_id   │───┐
│ name        │     │ name        │<────│ barcode     │   │
│ city        │     │ email       │     │ name        │   │
│ address     │     │ password    │     │ category    │   │
│ phone       │     │ role (spatie)│     │ price       │   │
│ is_active   │     └─────────────┘     │ stock       │   │
└─────────────┘                         │ min_stock   │   │
                                        └─────────────┘   │
                                                          │
┌─────────────┐     ┌─────────────┐     ┌─────────────┐   │
│transactions │     │transaction_ │     │ stock_logs  │   │
│             │     │  details    │     │             │   │
├─────────────┤     ├─────────────┤     ├─────────────┤   │
│ id (PK)     │────<│ transaction │     │ id (PK)     │   │
│ invoice_no  │     │   _id       │     │ product_id  │───┘
│ branch_id   │───┐ │ product_id  │────>│ type        │
│ cashier_id  │   │ │ quantity    │     │ quantity    │
│ date        │   │ │ price       │     │ stock_before│
│ subtotal    │   │ │ subtotal    │     │ stock_after │
│ tax         │   │ └─────────────┘     │ note        │
│ discount    │   │                     │ user_id     │
│ total       │   │                     └─────────────┘
│ cash        │   │
│ change      │   │
│ status      │   │
│ deleted_at  │   │
│ deleted_by  │   │
│ delete_reason│  │
└─────────────┘   │
                  │
        ┌─────────┴─────────┐
        │                   │
   ┌────┴────┐         ┌────┴────┐
   │ roles   │         │permiss- │
   │(spatie) │         │ions     │
   └─────────┘         │(spatie) │
                       └─────────┘
```

### Tabel Detail

| Tabel | Primary Key | Foreign Key | Soft Delete | Keterangan |
|-------|-------------|-------------|-------------|------------|
| branches | id | - | - | Data cabang |
| users | id | branch_id | - | Data pengguna |
| products | id | branch_id | ✅ | Data produk |
| transactions | id | branch_id, cashier_id | ✅ | Data transaksi |
| transaction_details | id | transaction_id, product_id | - | Detail transaksi |
| stock_logs | id | product_id, user_id | ✅ | Log stok |
| roles (spatie) | id | - | - | Role user |
| permissions (spatie) | id | - | - | Permission |

---

## 🔐 Akun Uji Coba

### Akun Owner

| Role | Email | Password |
|------|-------|----------|
| **Owner** | owner@minimarket.com | password123 |

### Akun Cabang Jakarta (JKT01)

| Role | Email | Password |
|------|-------|----------|
| **Manager** | manager.JKT01@minimarket.com | password123 |
| **Supervisor** | supervisor.JKT01@minimarket.com | password123 |
| **Kasir 1** | cashier1.JKT01@minimarket.com | password123 |
| **Kasir 2** | cashier2.JKT01@minimarket.com | password123 |
| **Warehouse** | warehouse.JKT01@minimarket.com | password123 |

### Akun Cabang Bandung (BDG01)

| Role | Email | Password |
|------|-------|----------|
| **Manager** | manager.BDG01@minimarket.com | password123 |
| **Supervisor** | supervisor.BDG01@minimarket.com | password123 |
| **Kasir 1** | cashier1.BDG01@minimarket.com | password123 |
| **Kasir 2** | cashier2.BDG01@minimarket.com | password123 |
| **Warehouse** | warehouse.BDG01@minimarket.com | password123 |

### Akun Cabang Surabaya (SBY01)

| Role | Email | Password |
|------|-------|----------|
| **Manager** | manager.SBY01@minimarket.com | password123 |
| **Supervisor** | supervisor.SBY01@minimarket.com | password123 |
| **Kasir 1** | cashier1.SBY01@minimarket.com | password123 |
| **Kasir 2** | cashier2.SBY01@minimarket.com | password123 |
| **Warehouse** | warehouse.SBY01@minimarket.com | password123 |

### Akun Cabang Semarang (SMG01)

| Role | Email | Password |
|------|-------|----------|
| **Manager** | manager.SMG01@minimarket.com | password123 |
| **Supervisor** | supervisor.SMG01@minimarket.com | password123 |
| **Kasir 1** | cashier1.SMG01@minimarket.com | password123 |
| **Kasir 2** | cashier2.SMG01@minimarket.com | password123 |
| **Warehouse** | warehouse.SMG01@minimarket.com | password123 |

### Akun Cabang Yogyakarta (YOG01)

| Role | Email | Password |
|------|-------|----------|
| **Manager** | manager.YOG01@minimarket.com | password123 |
| **Supervisor** | supervisor.YOG01@minimarket.com | password123 |
| **Kasir 1** | cashier1.YOG01@minimarket.com | password123 |
| **Kasir 2** | cashier2.YOG01@minimarket.com | password123 |
| **Warehouse** | warehouse.YOG01@minimarket.com | password123 |

> **Catatan:** Password default adalah `password123` dan pengguna **WAJIB mengganti password** saat pertama kali login. Owner dapat mereset password semua akun dalam satu cabang melalui menu Cabang → titik tiga → Reset Semua Password.

---

## 👥 Role dan Hak Akses

### Tabel Hak Akses per Role

| Fitur | Owner | Manager | Supervisor | Kasir | Warehouse |
|-------|-------|---------|------------|-------|-----------|
| **Dashboard** | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Lihat Semua Cabang** | ✅ | ❌ | ❌ | ❌ | ❌ |
| **Lihat Cabang Sendiri** | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Kelola Cabang** | ✅ | ❌ | ❌ | ❌ | ❌ |
| **Lihat Produk** | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Tambah/Edit Produk** | ✅ | ✅ | ❌ | ❌ | ❌ |
| **Hapus Produk** | ✅ | ✅ | ❌ | ❌ | ❌ |
| **Kelola Stok** | ✅ | ✅ | ❌ | ❌ | ✅ |
| **Lihat Transaksi** | ✅ | ✅ | ✅ | ✅ | ❌ |
| **Buat Transaksi** | ✅ | ✅ | ❌ | ✅ | ❌ |
| **Batalkan Transaksi** | ✅ | ✅ | ❌ | ❌ | ❌ |
| **Cetak Struk** | ✅ | ✅ | ✅ | ✅ | ❌ |
| **Laporan Harian** | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Laporan Bulanan** | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Laporan Stok** | ✅ | ✅ | ✅ | ❌ | ✅ |
| **Export Laporan** | ✅ | ✅ | ✅ | ❌ | ❌ |
| **Audit Trail** | ✅ | ❌ | ❌ | ❌ | ❌ |
| **Reset Password Cabang** | ✅ | ❌ | ❌ | ❌ | ❌ |

### Hierarki Role

```
                    OWNER (Bapak Jayusman)
                            │
              ┌─────────────┼─────────────┐
              │             │             │
              ▼             ▼             ▼
         MANAGER         MANAGER       MANAGER
         (Jakarta)       (Bandung)     (Surabaya)
              │             │             │
              ▼             ▼             ▼
         SUPERVISOR      SUPERVISOR    SUPERVISOR
         (Jakarta)       (Bandung)     (Surabaya)
              │             │             │
         ┌────┴────┐   ┌────┴────┐   ┌────┴────┐
         ▼         ▼   ▼         ▼   ▼         ▼
      KASIR    WAREHOUSE ...
```

---

## 📖 Cara Penggunaan

### 1. Login

1. Buka halaman login `http://localhost:8000/login`
2. Masukkan email dan password sesuai role dari tabel di atas
3. Jika pertama kali login (password default `password123`), akan diarahkan ke halaman ganti password
4. Setelah mengganti password, akan diarahkan ke Dashboard

### 2. Dashboard

- **Owner:** Melihat ringkasan semua cabang, bisa filter per cabang dari dropdown
- **Manager/Supervisor/Kasir/Warehouse:** Melihat ringkasan cabang sendiri (otomatis terfilter)

### 3. Manajemen Cabang (Khusus Owner)

1. Buka menu **Cabang**
2. Untuk menambah cabang baru: klik tombol **Tambah Cabang**
3. Untuk mengedit cabang: klik ikon **pensil** pada card cabang
4. Untuk toggle status aktif/nonaktif: klik ikon **power**
5. Untuk reset semua password di cabang: klik ikon **titik tiga (...)** → **Reset Semua Password**
6. Untuk melihat detail cabang: klik ikon **mata**

### 4. Manajemen Produk

1. Buka menu **Produk**
2. **Tambah Produk:** klik tombol **Tambah Produk** → isi form (barcode bisa generate otomatis dengan klik "Generate")
3. **Atur Stok:** klik ikon **kotak** pada produk → pilih tipe (Stok Masuk / Stok Keluar / Penyesuaian Stok) → isi jumlah → simpan
4. **Riwayat Stok:** klik ikon **history** untuk melihat log perubahan stok
5. **Filter:** bisa filter berdasarkan cabang (owner), kategori, dan status stok
6. **Pencarian:** cari produk berdasarkan nama atau barcode

### 5. Transaksi (POS)

> Hanya untuk role: Owner, Manager, Kasir

1. Buka menu **Transaksi Baru** (atau klik tombol hijau "Transaksi Baru" di pojok kanan)
2. **Tambah produk:** klik produk dari daftar di sebelah kiri, atau scan barcode menggunakan scanner
3. **Keranjang:** lihat item yang sudah ditambahkan di sebelah kanan
4. **Masukkan jumlah tunai:** sistem akan menghitung kembalian otomatis
5. **Catatan (opsional):** tambahkan catatan untuk transaksi
6. **Proses transaksi:** klik tombol hijau "Proses Transaksi" → konfirmasi
7. **Cetak struk:** setelah transaksi berhasil, akan muncul halaman struk dan otomatis membuka print dialog

### 6. Laporan

1. Buka menu **Laporan** (dropdown)
2. **Laporan Harian:**
   - Pilih tanggal yang diinginkan
   - Pilih cabang (khusus owner)
   - Klik "Tampilkan"
   - Export ke CSV/PDF dengan klik tombol "Export"
3. **Laporan Bulanan:**
   - Pilih bulan dan tahun
   - Pilih cabang (khusus owner)
   - Klik "Tampilkan"
   - Export ke CSV/PDF
4. **Laporan Stok:**
   - Gunakan filter cabang, kategori, dan status stok
   - Cari produk berdasarkan nama/barcode
   - Export ke CSV/PDF

### 7. Audit Trail (Khusus Owner)

1. Buka menu **Audit** → **Transaksi Dibatalkan**
   - Lihat semua transaksi yang dibatalkan
   - Filter berdasarkan cabang, tanggal, atau cari invoice
   - **Restore:** mengembalikan transaksi (stok akan dikurangi kembali)
   - **Hapus Permanen:** menghapus data selamanya
2. Buka menu **Audit** → **Produk Terhapus**
   - Lihat semua produk yang dihapus (soft delete)
   - Filter berdasarkan cabang atau pencarian
   - **Restore:** mengembalikan produk
   - **Hapus Permanen:** menghapus data selamanya

### 8. Profil

1. Klik nama user di pojok kanan atas
2. **Informasi Profil:** ubah nama dan email
3. **Keamanan Akun:** ganti password
   - Password baru minimal 8 karakter
   - Wajib diisi password saat ini
4. **Hapus Akun:** menghapus akun permanen (khusus untuk akun sendiri, bukan untuk orang lain)

---

## 📝 Catatan Penting

1. **Wajib Ganti Password:** Semua user dengan password default (`password123`) **WAJIB** mengganti password saat pertama kali login. Sistem akan redirect ke halaman profile.

2. **Soft Delete:** 
   - Produk yang sudah pernah bertransaksi hanya disembunyikan (soft delete) dan dapat dilihat di menu Audit
   - Transaksi yang dibatalkan hanya disembunyikan (soft delete) dan dapat dilihat di menu Audit
   - Data yang di-restore akan kembali normal (stok akan disesuaikan)

3. **Role dan Akses:**
   - **Owner:** Akses penuh ke semua cabang, bisa kelola cabang, audit trail
   - **Manager:** Kelola cabang sendiri, bisa batalkan transaksi (dengan alasan)
   - **Supervisor:** Hanya lihat (read-only), tidak bisa membuat atau membatalkan transaksi
   - **Kasir:** Hanya membuat transaksi (tidak bisa membatalkan)
   - **Warehouse:** Hanya kelola stok produk

4. **Pajak:** Sistem otomatis menghitung pajak 11% dari subtotal (PPN)

5. **Barcode Format:** Format barcode default: `899` + `timestamp` + `random` (total 13 digit)

6. **Invoice Format:** Format invoice: `INV/YYYYMMDD/XXXXXX` (contoh: `INV/20240610/000001`)

7. **Audit Log:** Setiap pembatalan transaksi mencatat siapa yang membatalkan dan alasan pembatalan

---

## 📄 Lisensi

Aplikasi ini dikembangkan untuk **PT. Jayusman Group** sebagai solusi internal perusahaan.

| Hak | Status |
|-----|--------|
| Digunakan untuk operasional internal PT. Jayusman Group | ✅ Diizinkan |
| Didistribusikan secara publik | ❌ Tidak diizinkan |
| Dijual atau dikomersialkan | ❌ Tidak diizinkan |
| Dimodifikasi dan diklaim sebagai milik pihak lain | ❌ Tidak diizinkan |

---

## 👨‍💻 Kontak Developer

| Kontak | Informasi |
|--------|-----------|
| 📧 Email | developer@jayusman.com |
| 🌐 Website | https://minimarket.jayusman.com |
| 📞 Telepon | (021) 1234-5678 |

---

## 🙏 Ucapan Terima Kasih

Terima kasih kepada:

- **Bapak Jayusman** - Atas kepercayaan dan dukungannya
- **Tim Manajemen** - Atas masukan dan feedback yang berharga
- **Seluruh Karyawan** - Atas partisipasi dalam uji coba aplikasi

---

<div align="center">
    <img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="200" alt="Laravel Logo">
    <br>
    <sub>Built with ❤️ for Bapak Jayusman</sub>
    <br>
    <sub>Sistem Manajemen Mini Market Terintegrasi | Version 1.0.0</sub>
    <br>
    <sub>© 2024 PT. Jayusman Group - All Rights Reserved</sub>
</div>
```
