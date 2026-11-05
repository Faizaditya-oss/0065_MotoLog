[README.md](https://github.com/user-attachments/files/34435700/README.md)
# MotoLog

**Sistem Manajemen Bengkel dengan Riwayat dan Rekomendasi Servis Berkala**

Project Akhir Mata Kuliah Pengembangan Aplikasi Mobile 2026



**Nama**: Faiz Aditya
**NIM**: 20240140065
**Kelas**: C


---

## Deskripsi

MotoLog adalah aplikasi mobile Android untuk mengelola operasional bengkel motor. Setiap motor memiliki catatan riwayat servis, mulai dari keluhan, mekanik yang menangani, sparepart yang dipakai, sampai total biaya. Dari riwayat tersebut, aplikasi menghitung **rekomendasi servis berkala** (misalnya ganti oli) berdasarkan kilometer terakhir dan tanggal servis sebelumnya.

### Latar Belakang

[Isi 2-3 kalimat: masalah yang ingin diselesaikan, misalnya pencatatan servis manual yang mudah hilang dan pelanggan yang lupa jadwal servis rutin.]

### Tujuan

- Mencatat data pelanggan, kendaraan, servis, dan stok sparepart secara terpusat.
- Menyediakan riwayat servis yang dapat ditelusuri per kendaraan.
- Memberi rekomendasi servis berikutnya berdasarkan data riwayat.

---

## Teknologi

| Bagian | Teknologi |
|---|---|
| Aplikasi Android | Kotlin, Jetpack Compose |
| Arsitektur | MVVM |
| Navigasi | Navigation Compose |
| Backend / REST API | [isi, misalnya Node.js + Express / Laravel / Spring Boot] |
| Database | MySQL |
| Autentikasi | JWT (access token) dan refresh token |
| File Storage | Penyimpanan file lokal (foto kendaraan, ekspor nota) |

---

## Peran Pengguna

| Peran | Hak Akses |
|---|---|
| **Admin** | Semua fitur, termasuk kelola user dan sparepart |
| **Mekanik** | Melihat servis yang ditugaskan, mengubah status, menambah sparepart ke servis |
| **Pelanggan** | Melihat motor dan riwayat servis milik sendiri |

> [Sesuaikan dengan keputusan akhir: 3 peran atau 2 peran (admin dan mekanik). Samakan dengan SRS.]

---

## Daftar Fitur dan Status

Status: `Belum` | `Proses` | `Selesai`

### Fitur Wajib

| No | Fitur | Keterangan | Status |
|---|---|---|---|
| 1 | Autentikasi | Login, register, access token (JWT), refresh token | Belum |
| 2 | Otorisasi | Tampilan dan hak akses berdasarkan peran | Belum |
| 3 | Navigasi | Multi-halaman dengan Navigation Compose | Belum |
| 4 | File Storage | Simpan dan baca foto kendaraan serta nota servis | Belum |

### Fitur CRUDS

| No | Fitur | Create | Read | Update | Delete | Search | Status |
|---|---|---|---|---|---|---|---|
| 1 | Pelanggan | - | - | - | - | - | Belum |
| 2 | Kendaraan | - | - | - | - | - | Belum |
| 3 | Servis | - | - | - | - | - | Belum |
| 4 | Sparepart | - | - | - | - | - | Belum |
| 5 | Pengelolaan User/Mekanik (admin) | - | - | - | - | - | Belum |

### Fitur Pembeda

| Fitur | Keterangan | Status |
|---|---|---|
| Rekomendasi servis berkala | Menghitung perkiraan servis berikutnya dari `km_terakhir` dan tanggal servis sebelumnya | Belum |

---

## Rancangan Data

### Entitas

| Entitas | Field Utama |
|---|---|
| User | id, nama, email, password_hash, role, foto_profil, refresh_token |
| Pelanggan | id, user_id, nama, no_hp, alamat |
| Kendaraan | id, pelanggan_id, plat_nomor, merk, tipe, tahun, warna, km_terakhir, foto |
| Servis | id, kendaraan_id, mekanik_id, tanggal_masuk, keluhan, status, km_saat_servis, total_biaya |
| Sparepart | id, kode, nama, kategori, stok, harga_beli, harga_jual |
| DetailServis | id, servis_id, sparepart_id, jumlah, harga_satuan |

### Relasi

- Pelanggan 1 : N Kendaraan
- Kendaraan 1 : N Servis
- User (mekanik) 1 : N Servis
- Servis N : M Sparepart (melalui DetailServis)

> ERD lengkap: [tambahkan gambar atau tautan setelah ERD dibuat]

---

## Struktur Project

> Rencana awal, dapat berubah selama pengerjaan.

```
4NIMBelakang_MotoLog/
├── app/                  # Aplikasi Android (Jetpack Compose)
│   └── src/main/java/.../
│       ├── data/         # API service, model, repository
│       ├── ui/           # Screen dan komponen Compose
│       ├── viewmodel/    # ViewModel (MVVM)
│       └── navigation/   # Rute Navigation Compose
├── backend/              # REST API
├── docs/                 # SRS, ERD, wireframe
└── README.md
```

---

## Cara Menjalankan

> Diisi saat project sudah dapat dijalankan.

### Backend

```
[perintah instalasi dan menjalankan server]
```

### Aplikasi Android

1. Buka folder `app` di Android Studio.
2. Atur alamat base URL API di [isi lokasi file konfigurasi].
3. Jalankan di emulator atau perangkat.

---

## Dokumentasi

- SRS: [tautan ke `docs/`]
- Wireframe: [tautan]
- Daftar endpoint API: [tautan]

---

## Log Progress Mingguan

| Minggu | Tanggal | Progress | Status |
|---|---|---|---|
| 1 | [tanggal] | Menentukan judul, membuat repository dan README awal | Selesai |
| 2 | [tanggal] | [Contoh: penyusunan SRS dan ERD] | Belum |
| 3 | [tanggal] | [Contoh: desain database dan daftar endpoint API] | Belum |
| 4 | [tanggal] | [isi] | Belum |

> Tambahkan satu baris baru setiap minggu dan lakukan commit.
