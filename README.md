# README.md

## Praktikum Pertemuan 13

### Stored Procedure, Trigger, dan View pada Database Sistem Sidang Tugas Akhir

---

## Deskripsi

Praktikum ini bertujuan untuk mempelajari implementasi **View**, **Stored Procedure**, **Trigger**, dan **Query Laporan** pada database **Sistem Sidang Tugas Akhir** menggunakan MariaDB/MySQL. Praktikum ini membantu mahasiswa memahami bagaimana mengotomatisasi proses pengolahan data, menampilkan informasi dari beberapa tabel, serta mencatat aktivitas database secara otomatis. 

---

## Tujuan Praktikum

* Membuat **View** untuk menampilkan jadwal sidang.
* Membuat **Stored Procedure** untuk menambahkan jadwal sidang.
* Membuat **Trigger** untuk mencatat log aktivitas.
* Membuat laporan menggunakan query SQL.
* Mengimplementasikan pengecekan bentrok jadwal ruangan.
* Membuat view daftar dosen penguji.
* Membuat laporan jumlah sidang setiap hari. 

---

## Software yang Digunakan

* MariaDB / MySQL
* XAMPP atau Laragon
* MySQL Command Line / phpMyAdmin
* Visual Studio Code (opsional)
* Sistem Operasi Windows

---

## Struktur Database

Database yang digunakan bernama **`sidang_ta`** dengan tabel:

* `mahasiswa`
* `dosen`
* `ruangan`
* `sidang`
* `penguji`
* `log_activity` 

---

## Fitur yang Diimplementasikan

### 1. View `v_jadwal_sidang`

Menampilkan informasi:

* NIM
* Nama Mahasiswa
* Program Studi
* Tanggal Sidang
* Jam Sidang
* Nama Ruangan

```sql
SELECT * FROM v_jadwal_sidang;
```

---

### 2. Stored Procedure `sp_tambah_sidang`

Digunakan untuk menambahkan data sidang dengan parameter:

* ID Mahasiswa
* Tanggal Sidang
* Jam Mulai
* Jam Selesai
* ID Ruangan

Contoh penggunaan:

```sql
CALL sp_tambah_sidang(
1,
'2026-07-10',
'08:00:00',
'09:30:00',
1
);
```

---

### 3. Trigger `trg_log_sidang`

Trigger akan berjalan secara otomatis setiap kali terdapat penambahan data pada tabel **sidang** dan mencatat aktivitas tersebut ke tabel **log_activity**.

---

### 4. Query Laporan

Menampilkan mahasiswa yang belum memiliki jadwal sidang.

```sql
SELECT *
FROM mahasiswa
WHERE id_mahasiswa NOT IN(
SELECT id_mahasiswa
FROM sidang
);
```

---

### 5. Tugas Individu

Implementasi tambahan meliputi:

* Stored Procedure untuk mengecek bentrok jadwal ruangan.
* Trigger ketika data sidang dihapus.
* View daftar dosen penguji.
* Laporan jumlah sidang per hari. 

---

## Hasil Praktikum

Seluruh objek database berhasil dibuat dan dijalankan, antara lain:

* Database `sidang_ta`
* View `v_jadwal_sidang`
* Stored Procedure `sp_tambah_sidang`
* Trigger `trg_log_sidang`
* Trigger `trg_hapus_sidang`
* View `v_dosen_penguji`
* Query laporan mahasiswa yang belum memiliki jadwal sidang
* Laporan jumlah sidang setiap hari

---

## Kesimpulan

Berdasarkan hasil praktikum dapat disimpulkan bahwa:

* **View** memudahkan penyajian data dari beberapa tabel.
* **Stored Procedure** menyederhanakan proses input data dan dapat digunakan kembali.
* **Trigger** mampu menjalankan proses otomatis untuk pencatatan aktivitas database.
* Query laporan membantu menghasilkan informasi yang dibutuhkan pengguna.
* Implementasi pengecekan bentrok jadwal meningkatkan validasi data sehingga jadwal sidang menjadi lebih teratur.
* Praktikum ini memberikan pemahaman mengenai pemanfaatan fitur-fitur lanjutan MariaDB/MySQL dalam membangun sistem informasi yang lebih efisien dan terstruktur.

---

## Dokumentasi

Lampirkan screenshot berikut sebagai bukti pengerjaan:

1. Pembuatan database.
2. Struktur tabel.
3. Pembuatan View.
4. Pembuatan Stored Procedure.
5. Pembuatan Trigger.
6. Hasil `CALL sp_tambah_sidang`.
7. Isi tabel `sidang`.
8. Isi tabel `log_activity`.
9. Hasil `SELECT * FROM v_jadwal_sidang`.
10. Hasil laporan mahasiswa yang belum memiliki jadwal sidang.
11. Hasil View dosen penguji.
12. Hasil laporan jumlah sidang per hari.

---


**Tahun 2026**
