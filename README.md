# Coffe Sedayu - Parking System

Sistem Manajemen Parkir berbasis web modern yang dirancang khusus untuk mengelola area parkir, pencatatan kendaraan masuk/keluar, pembayaran mandiri oleh pelanggan, serta laporan riwayat transaksi secara real-time. Project ini dikembangkan menggunakan **PHP Native (PDO)**, **Tailwind CSS**, dan **MySQL**.

---

## 🚀 Fitur Utama

### 1. **Role & Hak Akses (Multi-user)**
* **Admin / Petugas:** 
  * Mengelola pintu kendaraan masuk dan keluar.
  * Memproses pembayaran parkir (Tunai, Transfer Bank, QRIS).
  * Memantau kapasitas dan ketersediaan slot parkir secara langsung.
* **Pelanggan (Member):**
  * Memantau ketersediaan slot parkir di area Coffe Sedayu.
  * Melakukan **Checkout & Pembayaran Mandiri** secara online melalui dashboard.
  * Melihat riwayat kunjungan lengkap dengan fitur pencarian dan filter tanggal.
  * Mengunduh riwayat kunjungan dalam format CSV.

### 2. **Sistem Perhitungan Tarif Otomatis**
* Sistem menghitung durasi parkir berdasarkan selisih waktu masuk dan waktu keluar secara otomatis.
* Dilengkapi dengan sistem *fallback* tarif dasar (misal: Rp 2.000/jam) guna menghindari error nominal kosong (`Rp 0`) pada transaksi.

### 3. **Fitur Pendukung**
* **Struk Digital & Cetak:** Struk pembayaran dirancang khusus agar siap cetak (`window.print()`).
* **Log Aktivitas:** Mencatat setiap aktivitas penting pengguna untuk kebutuhan audit sistem.
* **Desain Responsif:** Dibangun menggunakan kerangka kerja Tailwind CSS dengan tema gelap (*dark mode*) yang elegan.

---

## 🛠️ Teknologi yang Digunakan

* **Backend:** PHP 8+ (Native dengan ekstensi PDO)
* **Database:** MySQL / MariaDB
* **Frontend:** Tailwind CSS (via CDN), FontAwesome 6.4.0
* **Server Lokal:** XAMPP / Laragon (Apache)

---

## 📁 Struktur Direktori Project

```text
coffe-sedayu/
├── config.php            # Konfigurasi koneksi database & fungsi helper
├── auth.php              # Sistem autentikasi & hak akses role
├── sidebar.php           # Komponen navigasi samping (sidebar)
├── pelanggan.php         # Dashboard & pembayaran mandiri pelanggan
├── kendaraan_keluar.php  # Modul proses keluar kendaraan (Petugas/Admin)
├── kendaraan_masuk.php   # Modul pencatatan kendaraan masuk
├── export_riwayat...     # Fitur ekspor laporan ke CSV
└── README.md             # Dokumentasi project
⚙️ Cara Instalasi & Menjalankan Project
Clone atau Unduh Repository:
Letakkan folder project ke dalam direktori server lokal Anda (contoh: htdocs pada XAMPP atau www pada Laragon).

Konfigurasi Database:

Buat database baru di MySQL melalui phpMyAdmin dengan nama (misal: parkir_coffe_sedayu).

Impor file struktur SQL project ke dalam database tersebut.

Pengaturan Koneksi:

Sesuaikan kredensial database (host, username, password, nama database) di dalam file config.php.

Menjalankan Aplikasi:

Nyalakan Apache dan MySQL melalui control panel XAMPP/Laragon.

Buka browser dan akses URL: http://localhost/coffe-sedayu/

👨‍💻 Pembuat
Project ini dikembangkan oleh Narendra Abdhil sebagai bagian dari Uji Kompetensi Keahlian (UKK).
