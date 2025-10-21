# Sistem Manajemen Pegawai

Aplikasi web berbasis **Laravel** untuk mengelola data **pegawai**, **absensi**, dan **kinerja**, serta menampilkan **dashboard ringkasan** seperti jumlah pegawai aktif, persentase kehadiran harian, dan pegawai dengan nilai kinerja tertinggi dan terendah.

---

## Fitur Utama

### Modul Pegawai
- CRUD (Create, Read, Update, Delete) data pegawai.
- Upload foto pegawai (tersimpan di `storage/app/public/foto_pegawai`).
- Pencarian berdasarkan **nama, NIP, jabatan, dan unit kerja**.
- Filter berdasarkan **status kepegawaian** (Aktif, Cuti, Tidak Aktif).
- Validasi input:  
  - NIP wajib unik dan numerik.  
  - Foto opsional (maksimal 2MB, format gambar).  

### Modul Absensi
- Input dan pelacakan absensi harian pegawai.
- Menentukan waktu masuk dan pulang.
- Status kehadiran: Hadir, Izin, Sakit, Alpha, Cuti.
- Tersedia kolom keterangan tambahan.
- Data absensi terhubung langsung dengan data pegawai.

### Modul Kinerja
- Penilaian kinerja per pegawai.
- Rentang nilai **1 – 10**.
- Periode kinerja (tanggal mulai dan selesai) disimpan dalam satu kolom.
- Deskripsi kinerja dapat berisi **beberapa poin (list)**.
- Dashboard menampilkan pegawai dengan nilai **tertinggi** dan **terendah**.

### Dashboard
Menampilkan ringkasan utama:
- Jumlah pegawai **aktif**.
- Persentase **kehadiran hari ini**.
- Pegawai dengan nilai **kinerja tertinggi** dan **terendah**.
- Tanggal hari ini secara otomatis.

---

## Teknologi yang Digunakan

| Komponen | Teknologi |
|-----------|------------|
| Framework Backend | Laravel 11 |
| Database | MySQL |
| Template Engine | Blade |
| Frontend | Bootstrap 5 |
| Storage | Laravel Filesystem (Public Disk) |
| Validasi | Laravel Validation |

---

## Instalasi

### 1️ Clone Repository
- git clone https://github.com/ErlanggaNapit16/Manajemen-Pegawai.git
- cd Manajemen-Pegawai

   
### 2️ Install Dependencies
- composer install
- npm install && npm run build

### 3 Salin File .env
cp .env.example .env

### 4 Konfigurasi Database di .env
- DB_DATABASE=manajemen_pegawai
- DB_USERNAME=root
- DB_PASSWORD=

###  5 Jalankan migrasi database
php artisan migrate

### 6 Link Storage (untuk upload foto)
php artisan storage:link

### 7 Jalankan Server
php artisan serve
