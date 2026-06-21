# 🎬 Sistem Pemesanan Tiket Bioskop (Dart OOP)

## 👤 Identitas

### **Nama:** Aneka Lisda
### **NIM:** 25141013P
### **Kelas:** SI2KR
### **Mata Kuliah:** Pemrograman Berorientasi Objek (OOP)

---

## 📖 Deskripsi Program

Program ini merupakan simulasi **Sistem Pemesanan Tiket Bioskop** yang dibuat menggunakan bahasa pemrograman **Dart** dengan menerapkan konsep **Object Oriented Programming (OOP)**.

Sistem memungkinkan pengguna untuk:

* Melihat informasi film.
* Melihat data pelanggan.
* Memilih kursi bioskop.
* Membuat pesanan tiket.
* Melakukan pembayaran.
* Menampilkan detail transaksi.

---

## 🎯 Tujuan Program

1. Memahami penerapan konsep OOP menggunakan Dart.
2. Mengimplementasikan class dan object.
3. Menggunakan relasi antar class.
4. Membuat simulasi proses pemesanan tiket bioskop.

---

## 🏗️ Struktur Class

Program terdiri dari 5 class utama:

### 1. Class Film

Digunakan untuk menyimpan informasi film.

**Atribut:**

* idFilm
* judul
* genre
* studio
* tanggal
* jadwal
* hargaTiket

**Method:**

* tampilkanFilm()

---

### 2. Class Pelanggan

Digunakan untuk menyimpan data pelanggan.

**Atribut:**

* idPelanggan
* nama

**Method:**

* tampilkanPelanggan()

---

### 3. Class Kursi

Digunakan untuk mengelola status kursi bioskop.

**Atribut:**

* nomorKursi
* tersedia (boolean)

**Method:**

* tampilkanStatus()
* pilihKursi()

---

### 4. Class Pesanan

Digunakan untuk menyimpan data pemesanan tiket.

**Atribut:**

* idPesanan
* kodeBooking
* tanggalPesan
* pelanggan
* film
* kursi
* jumlahTiket
* totalHarga
* statusPesanan

**Method:**

* tampilkanPesanan()

---

### 5. Class Pembayaran

Digunakan untuk menyimpan data pembayaran.

**Atribut:**

* idBayar
* metode
* totalBayar
* status

**Method:**

* tampilkanPembayaran()

---

## 🔄 Relasi Antar Class

Film
↓
Pesanan
↑
Pelanggan

Pesanan
↓
Kursi

Pesanan
↓
Pembayaran

---

## 💡 Konsep OOP yang Digunakan

### 1. Class

Digunakan untuk membuat blueprint objek.

Contoh:

```dart
class Film {
  String idFilm;
  String judul;
}
```

### 2. Object

Objek dibuat dari class.

Contoh:

```dart
Film film1 = Film(
  "F001",
  "Avengers Endgame",
  "Action",
  "Studio 1",
  "20 Juni 2026",
  "19.00 WIB",
  50000,
);
```

### 3. Constructor

Digunakan untuk menginisialisasi objek.

Contoh:

```dart
Film(this.idFilm, this.judul, this.genre,
     this.studio, this.tanggal,
     this.jadwal, this.hargaTiket);
```

### 4. Encapsulation

Data dan method digabungkan dalam satu class.

Contoh:

```dart
class Kursi {
  String nomorKursi;
  bool tersedia;

  void pilihKursi() {
    ...
  }
}
```

### 5. Association

Class Pesanan berhubungan dengan class lain.

Contoh:

```dart
Pelanggan pelanggan;
Film film;
Kursi kursi;
```


```
[Klik di sini untuk menjalankan kode DartPad](https://dartpad.dev/a6ad0d3de2cefbea2e4c2fe3d5e4e35b)
---


## 📋 Contoh Output

```text
====================================
 SISTEM PEMESANAN TIKET BIOSKOP
====================================

===== DATA FILM =====
ID Film       : F001
Judul         : Avengers Endgame
Genre         : Action
Studio        : Studio 1
Tanggal       : 20 Juni 2026
Jadwal        : 19.00 WIB
Harga Tiket   : Rp50000

===== DATA PELANGGAN =====
ID Pelanggan  : P001
Nama          : Aneka Lisda

===== DAFTAR KURSI =====
Kursi A1 : Tersedia
Kursi A2 : Tersedia
Kursi A3 : Tersedia

===== PEMILIHAN KURSI =====
Kursi A1 berhasil dipilih.

===== DETAIL PESANAN =====
ID Pesanan    : PS001
Kode Booking  : BK001
Tanggal Pesan : 13 Juni 2026
Pelanggan     : Aneka Lisda
Film          : Avengers Endgame
Studio        : Studio 1
Kursi         : A1
Jumlah Tiket  : 1
Total Bayar   : Rp50000
Status        : Tiket Berhasil Dipesan

===== PEMBAYARAN =====
ID Bayar      : BY001
Metode        : E-Wallet
Total Bayar   : Rp50000
Status        : Lunas

Terima kasih telah menggunakan layanan bioskop.
```

---

## ✅ Kesimpulan

Program Sistem Pemesanan Tiket Bioskop berhasil dibuat menggunakan bahasa Dart dengan menerapkan konsep Object Oriented Programming (OOP). Program ini mampu mengelola data film, pelanggan, kursi, pesanan, dan pembayaran secara terstruktur sehingga memudahkan proses pemesanan tiket bioskop.
