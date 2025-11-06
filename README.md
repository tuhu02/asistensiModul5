# Challenge Asistensi Modul 5

##  Deskripsi Umum
Proyek ini merupakan latihan pembuatan aplikasi **Login dan Registrasi Multi Level User** menggunakan **PHP dan MySQL**.  
Aplikasi akan menggunakan database `store2` yang telah disediakan (`store2.sql`).

Setiap pengguna memiliki **role (level)** berbeda yang menentukan halaman dashboard yang diakses setelah login.

---

##  Struktur Database

Gunakan database **`store2`** dengan tabel utama:
- **user**
  - `id_user` (Primary Key)
  - `username`
  - `password`
  - `nama`
  - `alamat`
  - `hp`
  - `level`  

### Keterangan Level:
| Level | Role  | Keterangan |
|--------|--------|------------|
| 1 | Admin | Memiliki akses penuh ke sistem |
| 2 | Kasir | Mengelola transaksi dan pembayaran |
| 3 | Staf | Pengguna umum hasil pendaftaran |

---

##  Fitur 1 — Form Login

### Tujuan
Membuat halaman login untuk memverifikasi data user berdasarkan tabel `user`.

### Kebutuhan
- Input: **username** dan **password**
- Tombol: **Login**

### Ketentuan
1. Jika username dan password cocok → tampilkan dashboard sesuai **level user**.
2. Jika salah → tampilkan pesan:
- Arahkan kembali ke halaman login setelah registrasi berhasil.

---

##  Alur Program

1. User membuka **login.php**
2. Jika belum punya akun → klik link **“Daftar di sini”** menuju **daftar.php**
3. Isi form pendaftaran → data tersimpan ke tabel `user`
4. Login dengan username dan password yang telah dibuat
5. Sistem mengecek level user:
 - Level 1 → **dashboard_admin.php**
 - Level 2 → **dashboard_kasir.php**
 - Level 3 → **dashboard_staf.php**
6. Di dashboard, tampilkan ucapan sesuai role dan nama user.

---

##  File yang Harus Dibuat

| Nama File | Fungsi |
|------------|---------|
| `koneksi.php` | File koneksi database ke MySQL |
| `login.php` | Halaman login dan autentikasi user |
| `daftar.php` | Form pendaftaran user baru |
| `dashboard_admin.php` | Dashboard untuk admin |
| `dashboard_kasir.php` | Dashboard untuk kasir |
| `dashboard_staf.php` | Dashboard untuk staf |

---

##  Contoh Pesan Dashboard

| Role | Pesan |
|------|--------|
| Admin | Selamat datang admin **[nama user]** |
| Kasir | Selamat datang kasir **[nama user]** |
| Staf | Selamat datang staf **[nama user]** |

---

##  Panduan Teknis

1. Import database `store2.sql` ke **phpMyAdmin**.
2. Simpan semua file PHP dalam satu folder di direktori:


##  Fitur 2 — Form Registrasi

###  Tujuan
Fitur ini digunakan agar **pengguna baru dapat membuat akun** di sistem.  
Data yang diisi pada form akan disimpan ke dalam tabel `user` di database `store2`.

---

###  Kebutuhan Fitur
Form registrasi terdiri dari beberapa input yang mewakili kolom di tabel `user`, yaitu:

| Nama Input | Kolom Database | Keterangan |
|-------------|----------------|-------------|
| `username` | username | Nama pengguna untuk login |
| `password` | password | Kata sandi |
| `nama` | nama | Nama lengkap pengguna |
| `alamat` | alamat | Alamat tempat tinggal pengguna |
| `hp` | hp | Nomor handphone pengguna |
| `level` | level | Menentukan peran user dalam sistem (Admin, Kasir, atau Staf) |

---

###  Ketentuan dan Alur Kerja
1. **User membuka halaman `daftar.php`**  
   Halaman ini berisi form untuk mendaftarkan akun baru.

2. **User mengisi seluruh field dengan lengkap.**

3. Setelah tombol **Daftar / Register** diklik:
   - Data dikirim ke database `store2`, tabel `user`.
   - Secara umum, user baru otomatis memiliki **level 3 (Staf)**, kecuali ditentukan lain.

4. Jika pendaftaran berhasil:
   - Tampilkan pesan:  
     > “Pendaftaran berhasil! Silakan login.”
   - Arahkan user ke halaman **`login.php`**.

5. Jika username sudah digunakan:
   - Tampilkan pesan kesalahan:  
     > “Username sudah terdaftar, silakan gunakan username lain.”

---

###  Hasil Akhir
Jika fitur ini berjalan dengan benar:
- User baru dapat **membuat akun sendiri**.  
- Data user tersimpan di **tabel `user`** pada **database `store2`**.  
- Setelah registrasi, user dapat **login** dan diarahkan ke **dashboard** sesuai level-nya.

---
