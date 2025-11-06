# 🧩 Tugas PHP MySQL - Form Login & Registrasi Multi Level User

## 📘 Deskripsi Umum
Proyek ini merupakan latihan pembuatan aplikasi **Login dan Registrasi Multi Level User** menggunakan **PHP dan MySQL**.  
Aplikasi akan menggunakan database `store2` yang telah disediakan (`store2.sql`).

Setiap pengguna memiliki **role (level)** berbeda yang menentukan halaman dashboard yang diakses setelah login.

---

## 🗃️ Struktur Database

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

## 🔐 Fitur 1 — Form Login

### Tujuan
Membuat halaman login untuk memverifikasi data user berdasarkan tabel `user`.

### Kebutuhan
- Input: **username** dan **password**
- Tombol: **Login**

### Ketentuan
1. Jika username dan password cocok → tampilkan dashboard sesuai **level user**.
2. Jika salah → tampilkan pesan:
