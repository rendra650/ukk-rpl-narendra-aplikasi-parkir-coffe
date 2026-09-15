# Coffe Sedayu - Parking System

Sistem Manajemen Parkir berbasis web modern yang dirancang khusus untuk mengelola area parkir, pencatatan kendaraan masuk/keluar, pembayaran mandiri oleh pelanggan, serta laporan riwayat transaksi secara real-time. Project ini dikembangkan menggunakan **PHP Native (PDO)**, **Tailwind CSS**, dan **MySQL**.
## 📐 Algoritma & Alur Sistem (Flowchart)

Sistem Parkir Coffe Sedayu dirancang dengan alur kerja sebagai berikut:
1. **Kendaraan Masuk:**
   * Petugas mencatat nomor plat dan jenis kendaraan di menu *Kendaraan Masuk*.
   * Sistem otomatis men-generate **Kode Tiket unik** dan mencatat waktu masuk (`waktu_masuk`).
2. **Kendaraan Keluar & Pembayaran:**
   * Petugas memasukkan atau memindai *Kode Tiket* pada menu *Kendaraan Keluar*.
   * Sistem menghitung durasi parkir (selisih waktu masuk dan waktu keluar) secara otomatis[cite: 3].
   * Total biaya dihitung dengan rumus: $\text{Total Bayar} = \text{Durasi (Jam)} \times \text{Tarif Dasar}$.
   * Pengguna memilih metode pembayaran (**Tunai, Transfer Bank, atau QRIS**)[cite: 3].
   * Sistem memperbarui status transaksi menjadi `keluar` dan struk siap dicetak[cite: 3].
---
<a href="https://github.com/user-attachments/assets/8e895ab7-c388-4912-b2cf-8c453a62edbc" target="_blank" style="display: inline-block; background-color: #159957; color: white; padding: 10px 20px; border-radius: 6px; text-decoration: none; font-weight: bold;">🖼️ Lihat Mockup Aplikasi Parkir</a>
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
* **Database:** MySQL
* **Frontend:** Tailwind CSS (via CDN), FontAwesome 6.4.0
* **Server Lokal:** XAMPP (Apache)

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

Nyalakan Apache dan MySQL melalui control panel XAMPP

Buka browser dan akses URL: http://localhost/coffe-sedayu/

👨‍💻 Pembuat
Project ini dikembangkan oleh Narendra Abdhil sebagai bagian dari Uji Kompetensi Keahlian (UKK).
