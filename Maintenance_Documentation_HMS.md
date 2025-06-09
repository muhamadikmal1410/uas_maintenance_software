# Maintenance Documentation

## 1. Project Title: Hospital Management System
- Version: v1.0
- Repository URL: https://github.com/hosiptal-system/sample-hms
- Nama Penyusun: Muhamad Ikmal Nuroddin
- Tanggal Pembuatan: Juni 2025

## 2. Deskripsi Umum Aplikasi
Hospital Management System (HMS) adalah aplikasi web berbasis PHP & MySQL yang digunakan untuk mengelola data pasien, dokter, jadwal konsultasi, rekam medis, dan pengelolaan rawat inap.

**Fitur Utama:**
- Manajemen pasien & dokter
- Booking konsultasi
- Pencatatan rekam medis
- Laporan kunjungan dan pendapatan

**Teknologi yang Digunakan:**
- Backend: PHP 7.4+
- Frontend: HTML5, CSS3, JavaScript, Bootstrap 4
- Database: MySQL
- Web Server: Apache 2.4
- OS: Linux/Windows

## 3. Struktur Folder dan File
```
hospital-system/
├── config/           # File konfigurasi database
├── controllers/      # Logika bisnis aplikasi
├── views/            # Halaman HTML/Template
├── public/           # Aset publik (JS, CSS, gambar)
├── logs/             # File log aplikasi
├── index.php         # Entry point utama
├── README.md
└── .env              # Konfigurasi environment
```

## 4. Instruksi Instalasi dan Konfigurasi

**Prasyarat:**
- PHP >= 7.4
- MySQL/MariaDB
- Apache Web Server
- Composer

**Langkah Instalasi:**
1. Clone repositori:
    ```bash
    git clone https://github.com/yourname/hospital-system.git
    ```
2. Import database: Buat database `hms_db` lalu import file `hms_db.sql`
3. Konfigurasi file `.env`:
    ```
    DB_HOST=localhost
    DB_USER=root
    DB_PASS=
    DB_NAME=hms_db
    ```
4. Jalankan server lokal:
    ```bash
    php -S localhost:8000
    ```

## 5. Dependency yang Digunakan

| Dependency     | Versi     | Keterangan        |
|----------------|-----------|-------------------|
| Bootstrap      | 4.6.2     | UI Framework      |
| jQuery         | 3.5.1     | DOM manipulation  |
| FontAwesome    | 5.15.4    | Ikon              |
| PHP dotenv     | 5.4       | Config .env       |

## 6. Instruksi Build dan Deployment

**Build (dev):**
```bash
php -S localhost:8000
```

**Deployment:**
1. Upload ke `/var/www/hms`
2. Atur permission folder `logs/`
3. Konfigurasi `.env`
4. Restart Apache:
    ```bash
    sudo systemctl restart apache2
    ```

**Backup Data:**
```bash
mysqldump -u root -p hms_db > backup.sql
```

## 7. Panduan Debugging dan Logging

**Debugging:**
- Aktifkan `display_errors`
- Gunakan `var_dump()` atau `error_log()`

**Logging:**
- File log: `logs/error.log`
- Format log:
    ```
    [2025-06-09 15:00:21] ERROR: Gagal menyimpan data pasien.
    ```

**Tools:**
- Xdebug
- Chrome DevTools

## 8. Catatan Perubahan (Change Log)

| Tanggal      | Versi | Deskripsi Perubahan                      | Developer     |
|--------------|-------|-------------------------------------------|---------------|
| 2025-06-07   | 1.0   | Initial release aplikasi HMS              | Ikmal         |
| 2025-06-09   | 1.1   | Tambah fitur laporan pasien bulanan       | Ikmal         |

## 9. Daftar Bug Dikenal

| Bug                            | Severity | Deskripsi                     | Solusi Sementara     | Prioritas |
|--------------------------------|----------|-------------------------------|-----------------------|-----------|
| Validasi email tidak berjalan  | Medium   | Form input tidak valid email | Gunakan regex manual  | Tinggi    |
| Gagal upload file >2MB         | Low      | Server tolak file besar      | Tingkatkan php.ini    | Sedang    |

## 10. Saran Pengembangan/Peningkatan

- Tambah fitur autentikasi dua langkah (2FA)
- Optimasi performa: indexing database
- CI/CD dengan GitHub Actions
- Tambahkan unit testing (PHPUnit)
- Dokumentasi tambahan: API docs, panduan pengguna
