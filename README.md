# 🧩 Challenge Asistensi Modul 5  

## 📘 Deskripsi Umum  
Proyek ini merupakan latihan untuk membuat aplikasi **Login dan Registrasi Multi Level User** menggunakan **PHP dan MySQL**.  
Aplikasi akan menggunakan database **`store2`** yang sudah disediakan (`store2.sql`).  

Setiap pengguna memiliki **role (level)** yang menentukan halaman dashboard yang diakses setelah login.  

---

## ⚙️ Panduan Teknis  
1. Import file database `store2.sql` ke **phpMyAdmin**.  
2. Simpan semua file PHP dalam satu folder di direktori server (misalnya di `htdocs/store2/`).  

---

## 🗂️ Struktur Database  

Gunakan database **`store2`** dengan tabel utama:  

### Tabel `user`  
| Kolom | Keterangan |
|--------|-------------|
| `id_user` | Primary key |
| `username` | Nama pengguna |
| `password` | Kata sandi |
| `nama` | Nama lengkap |
| `alamat` | Alamat tempat tinggal |
| `hp` | Nomor handphone |
| `level` | Menentukan role user |

### Keterangan Level  
| Level | Role  | Hak Akses |
|--------|--------|------------|
| 1 | Admin | Akses penuh ke sistem |
| 2 | Kasir | Mengelola transaksi dan pembayaran |
| 3 | Staf | Pengguna umum hasil pendaftaran |

---

## 🔑 Fitur 1 — Form Login  

### 🎯 Tujuan  
Membuat halaman login untuk memverifikasi data user berdasarkan tabel `user`.  

### 🧱 Komponen Form  
- **Input:** `username` dan `password`  
- **Tombol:** `Login`  

### 📋 Ketentuan  
1. Jika username dan password cocok → arahkan ke dashboard sesuai **level user**.  
2. Jika data salah → tampilkan pesan error.  
3. Setelah registrasi berhasil → arahkan user kembali ke halaman login.  

---

## 🔄 Alur Program  

1. User membuka **`login.php`**.  
2. Jika belum punya akun, klik link **“Daftar di sini”** menuju **`daftar.php`**.  
3. Isi form pendaftaran, lalu data tersimpan ke tabel `user`.  
4. Login menggunakan username dan password yang sudah dibuat.  
5. Sistem mengecek level user:  
   - Level 1 → `dashboard_admin.php`  
   - Level 2 → `dashboard_kasir.php`  
   - Level 3 → `dashboard_staf.php`  
6. Dashboard menampilkan ucapan sesuai role dan nama user.  

---

## 📁 File yang Harus Dibuat  

| Nama File | Fungsi |
|------------|---------|
| `koneksi.php` | Menghubungkan aplikasi dengan database MySQL |
| `login.php` | Halaman login dan autentikasi user |
| `daftar.php` | Form pendaftaran user baru |
| `dashboard_admin.php` | Dashboard untuk admin |
| `dashboard_kasir.php` | Dashboard untuk kasir |
| `dashboard_staf.php` | Dashboard untuk staf |

---

## 💬 Contoh Pesan Dashboard  

| Role | Pesan |
|------|--------|
| Admin | Selamat datang admin **[nama user]** |
| Kasir | Selamat datang kasir **[nama user]** |
| Staf | Selamat datang staf **[nama user]** |

---

## 🧾 Fitur 2 — Form Registrasi  

### 🎯 Tujuan  
Fitur ini memungkinkan **pengguna baru membuat akun** di sistem.  
Data yang diisi melalui form akan disimpan di tabel `user` pada database `store2`.  

---

### 🧱 Komponen Form  
Form registrasi berisi input yang sesuai dengan kolom tabel `user`:  

| Nama Input | Kolom Database | Keterangan |
|-------------|----------------|-------------|
| `username` | username | Nama pengguna untuk login |
| `password` | password | Kata sandi |
| `nama` | nama | Nama lengkap pengguna |
| `alamat` | alamat | Alamat tempat tinggal |
| `hp` | hp | Nomor handphone |
| `level` | level | Peran user (Admin, Kasir, atau Staf) |

---

### 📋 Ketentuan dan Alur Kerja  

1. **User membuka halaman `daftar.php`.**  
   Menampilkan form untuk mendaftarkan akun baru.  

2. **User mengisi semua field dengan lengkap.**  

3. Setelah klik tombol **Daftar / Register**:  
   - Data dikirim dan disimpan ke tabel `user` di database `store2`.  
   - Secara default, user baru memiliki **level 3 (Staf)**, kecuali ditentukan lain.  

4. Jika pendaftaran berhasil:  
   > “Pendaftaran berhasil! Silakan login.”  
   Kemudian diarahkan ke **`login.php`**.  

5. Jika username sudah digunakan:  
   > “Username sudah terdaftar, silakan gunakan username lain.”  

---

### ✅ Hasil Akhir  
Jika fitur berjalan dengan benar:  
- Pengguna baru dapat **membuat akun sendiri**.  
- Data user tersimpan di tabel **`user`** pada database **`store2`**.  
- Setelah registrasi, user dapat **login** dan diarahkan ke **dashboard** sesuai level-nya.  

---
