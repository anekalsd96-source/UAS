## 🎬 Aplikasi Console Sistem Pemesanan Tiket Bioskop Menggunakan Dart OOP

### 👤 Identitas

#### **Nama:** Aneka Lisda
#### **NIM:** 25141013P
#### **Kelas:** SI2KR
#### **Mata Kuliah:** Pemrograman Berorientasi Objek 

---

### 📖 Deskripsi Program

Program ini merupakan simulasi **Sistem Pemesanan Tiket Bioskop** yang dibuat menggunakan bahasa pemrograman **Dart** dengan menerapkan konsep **Object Oriented Programming (OOP)**.

Sistem memungkinkan pengguna untuk:

* Melihat informasi film.
* Melihat data pelanggan.
* Memilih kursi bioskop.
* Membuat pesanan tiket.
* Melakukan pembayaran.
* Menampilkan detail transaksi.

---

### 🎯 Tujuan Program

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
```dart
class Film {
  String idFilm;
  String judul;
  String genre;
  String studio;
  String tanggal;
  String jadwal;
  int hargaTiket;

  Film(
    this.idFilm,
    this.judul,
    this.genre,
    this.studio,
    this.tanggal,
    this.jadwal,
    this.hargaTiket,
  );

  void tampilkanFilm() {
    print("===== DATA FILM =====");
    print("ID Film     : $idFilm");
    print("Judul       : $judul");
    print("Genre       : $genre");
    print("Studio      : $studio");
    print("Tanggal     : $tanggal");
    print("Jadwal      : $jadwal");
    print("Harga Tiket : Rp$hargaTiket");
  }
}

void main() {
  Film film1 = Film(
    "F001",
    "Avengers Endgame",
    "Action",
    "Studio 1",
    "20 Juni 2026",
    "19.00 WIB",
    50000,
  );

  film1.tampilkanFilm();
}
```
### Output :
<img width="959" height="464" alt="image" src="https://github.com/user-attachments/assets/20d9dbd8-da9d-41ec-bfef-965421c8b886" />
---

### Penjelasan

Class **Film** digunakan untuk menyimpan seluruh informasi mengenai film yang tersedia di bioskop. Class ini memiliki atribut seperti ID film, judul, genre, studio, tanggal tayang, jadwal, dan harga tiket. Constructor digunakan untuk menginisialisasi data film saat objek dibuat, sedangkan method **tampilkanFilm()** berfungsi menampilkan seluruh informasi film ke layar.


### 2. Class Pelanggan

Digunakan untuk menyimpan data pelanggan.

**Atribut:**

* idPelanggan
* nama

**Method:**

```dart
class Pelanggan {
  String idPelanggan;
  String nama;

  Pelanggan(this.idPelanggan, this.nama);

  void tampilkanPelanggan() {
    print("===== DATA PELANGGAN =====");
    print("ID Pelanggan : $idPelanggan");
    print("Nama         : $nama");
  }
}

void main() {
  Pelanggan pelanggan1 = Pelanggan(
    "P001",
    "Aneka Lisda",
  );

  pelanggan1.tampilkanPelanggan();
}
```
### Output :
<img width="959" height="466" alt="image" src="https://github.com/user-attachments/assets/e2ac7de3-f948-4bb3-83c8-deecaa8afb87" />

### Penjelasan

Class **Pelanggan** digunakan untuk menyimpan data pelanggan yang melakukan pemesanan tiket. Atribut yang dimiliki adalah **idPelanggan** dan **nama**. Constructor digunakan untuk mengisi data pelanggan ketika objek dibuat, sedangkan method **tampilkanPelanggan()** berfungsi menampilkan informasi pelanggan.

### 3. Class Kursi

Digunakan untuk mengelola status kursi bioskop.

**Atribut:**

* nomorKursi
* tersedia (boolean)

**Method:**

* tampilkanStatus()
* pilihKursi()
  
```dart
class Kursi {
  String nomorKursi;
  bool tersedia;

  Kursi(this.nomorKursi, this.tersedia);

  void tampilkanStatus() {
    print("Kursi $nomorKursi : ${tersedia ? "Tersedia" : "Terisi"}");
  }

  void pilihKursi() {
    if (tersedia) {
      tersedia = false;
      print("\nKursi $nomorKursi berhasil dipilih.");
    } else {
      print("\nMaaf, kursi $nomorKursi sudah terisi.");
    }
  }
}

void main() {
  Kursi kursi1 = Kursi("A1", true);

  print("===== STATUS KURSI =====");
  kursi1.tampilkanStatus();

  print("\n===== MEMILIH KURSI =====");
  kursi1.pilihKursi();

  print("\n===== STATUS KURSI SETELAH DIPILIH =====");
  kursi1.tampilkanStatus();
}
  
```
### Output :
<img width="959" height="468" alt="image" src="https://github.com/user-attachments/assets/a89d73eb-835b-4ce9-8369-69cc7c7113bd" />


### Penjelasan

Class **Kursi** digunakan untuk mengelola data kursi bioskop. Atribut **nomorKursi** menyimpan nomor kursi, sedangkan atribut **tersedia** bertipe boolean untuk menunjukkan apakah kursi masih tersedia atau sudah terisi. Method **tampilkanStatus()** menampilkan status kursi, sedangkan **pilihKursi()** digunakan untuk mengubah status kursi menjadi terisi ketika dipilih oleh pelanggan.
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

```dart
class Film {
  String idFilm;
  String judul;
  String studio;
  int hargaTiket;

  Film(this.idFilm, this.judul, this.studio, this.hargaTiket);
}

class Pelanggan {
  String idPelanggan;
  String nama;

  Pelanggan(this.idPelanggan, this.nama);
}

class Kursi {
  String nomorKursi;
  bool tersedia;

  Kursi(this.nomorKursi, this.tersedia);
}

class Pesanan {
  String idPesanan;
  String kodeBooking;
  String tanggalPesan;
  Pelanggan pelanggan;
  Film film;
  Kursi kursi;
  int jumlahTiket;
  int totalHarga;
  String statusPesanan;

  Pesanan(
    this.idPesanan,
    this.kodeBooking,
    this.tanggalPesan,
    this.pelanggan,
    this.film,
    this.kursi,
    this.jumlahTiket,
  )   : totalHarga = film.hargaTiket * jumlahTiket,
        statusPesanan = "Tiket Berhasil Dipesan";

  void tampilkanPesanan() {
    print("===== DETAIL PESANAN =====");
    print("ID Pesanan    : $idPesanan");
    print("Kode Booking  : $kodeBooking");
    print("Tanggal Pesan : $tanggalPesan");
    print("Pelanggan     : ${pelanggan.nama}");
    print("Film          : ${film.judul}");
    print("Studio        : ${film.studio}");
    print("Kursi         : ${kursi.nomorKursi}");
    print("Jumlah Tiket  : $jumlahTiket");
    print("Total Bayar   : Rp$totalHarga");
    print("Status        : $statusPesanan");
  }
}

void main() {
  Film film = Film(
    "F001",
    "Avengers Endgame",
    "Studio 1",
    50000,
  );

  Pelanggan pelanggan = Pelanggan(
    "P001",
    "Aneka Lisda",
  );

  Kursi kursi = Kursi(
    "A1",
    true,
  );

  Pesanan pesanan = Pesanan(
    "PS001",
    "BK001",
    "13 Juni 2026",
    pelanggan,
    film,
    kursi,
    1,
  );

  pesanan.tampilkanPesanan();
}
```
### Output :
<img width="940" height="476" alt="image" src="https://github.com/user-attachments/assets/a8ebad00-9ad9-4002-9757-f638fc628fe2" />

### Penjelasan

Class **Pesanan** merupakan class utama yang menghubungkan class **Film**, **Pelanggan**, dan **Kursi**. Class ini menyimpan seluruh informasi transaksi seperti ID pesanan, kode booking, tanggal pemesanan, data pelanggan, film yang dipilih, kursi yang dipilih, jumlah tiket, total harga, dan status pesanan. Method **tampilkanPesanan()** berfungsi menampilkan seluruh detail transaksi yang telah dibuat.
---

### 5. Class Pembayaran

Digunakan untuk menyimpan data pembayaran.

**Atribut:**

* idBayar
* metode
* totalBayar
* status

**Method:**

```dart
class Pembayaran {
  String idBayar;
  String metode;
  int totalBayar;
  String status;

  Pembayaran(
    this.idBayar,
    this.metode,
    this.totalBayar,
    this.status,
  );

  void tampilkanPembayaran() {
    print("===== PEMBAYARAN =====");
    print("ID Bayar      : $idBayar");
    print("Metode        : $metode");
    print("Total Bayar   : Rp$totalBayar");
    print("Status        : $status");
  }
}

void main() {
  Pembayaran bayar1 = Pembayaran(
    "BY001",
    "E-Wallet",
    50000,
    "Lunas",
  );

  bayar1.tampilkanPembayaran();
}

```
### Output :
<img width="959" height="472" alt="image" src="https://github.com/user-attachments/assets/1e512efe-4c7c-4660-b380-01f3b72aae63" />

### Penjelasan

Class **Pembayaran** digunakan untuk menyimpan informasi pembayaran tiket. Class ini memiliki atribut **idBayar**, **metode**, **totalBayar**, dan **status**. Method **tampilkanPembayaran()** berfungsi menampilkan informasi pembayaran yang telah dilakukan oleh pelanggan, seperti metode pembayaran, total yang dibayar, dan status pembayaran.
---

## 🔄 Relasi Antar Class
```text
+-----------+
| Pelanggan |
+-----------+
      |
      |
      v
+-----------+
|  Pesanan  |
+-----------+
   /      \
  v        v
Film     Kursi
  |
  v
Pembayaran
```
---

## 💡 Konsep OOP yang Digunakan

### 1. Class

Digunakan untuk membuat blueprint objek.

```dart
class Pembayaran {
  String idBayar;
  String metode;
  int totalBayar;
  String status;

  Pembayaran(
    this.idBayar,
    this.metode,
    this.totalBayar,
    this.status,
  );

  void tampilkanPembayaran() {
    print("===== PEMBAYARAN =====");
    print("ID Bayar      : $idBayar");
    print("Metode        : $metode");
    print("Total Bayar   : Rp$totalBayar");
    print("Status        : $status");
  }
}

void main() {
  Pembayaran bayar1 = Pembayaran(
    "BY001",
    "E-Wallet",
    50000,
    "Lunas",
  );

  bayar1.tampilkanPembayaran();
}


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
**Penjelasan:**
Class Pesanan memiliki hubungan dengan class Pelanggan, Film, dan Kursi karena objek-objek tersebut digunakan dalam proses pemesanan tiket.
---
## ▶️ Cara Menjalankan Program

1. Buka DartPad melalui https://dartpad.dev
2. Salin source code program.
3. Tempelkan pada editor DartPad.
4. Klik tombol **Run**.
5. Hasil program akan tampil pada panel output.

## 🔗 Link Program

[Klik di sini untuk menjalankan kode DartPad](https://dartpad.dev/a6ad0d3de2cefbea2e4c2fe3d5e4e35b)

## 🔗 Link Gist
[Klik di sini untuk menjalankan kode Gist](https://gist.github.com/anekalsd96-source/a6ad0d3de2cefbea2e4c2fe3d5e4e35b)


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
## 📸 Screenshot Output

<img width="959" height="550" alt="image" src="https://github.com/user-attachments/assets/a739d3b8-982a-45c9-bfbc-71fe8078e111" />
<img width="956" height="592" alt="image" src="https://github.com/user-attachments/assets/3d6d089f-3cba-4f05-bf1e-e3dfe68a023b" />

---

## ✅ Kesimpulan

Program Sistem Pemesanan Tiket Bioskop berhasil dibuat menggunakan bahasa Dart dengan menerapkan konsep Object Oriented Programming (OOP). Program ini mampu mengelola data film, pelanggan, kursi, pesanan, dan pembayaran secara terstruktur sehingga memudahkan proses pemesanan tiket bioskop.
