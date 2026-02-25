# PAB PERTEMUAN 4 - PART 5

# Pemrograman Aplikasi Bergerak - Shopping Cart App

Aplikasi Flutter sederhana yang menampilkan daftar produk dengan fitur keranjang belanja.  
Dibangun menggunakan **Flutter** dan **Provider** sebagai solusi manajemen state.

Aplikasi mencakup fitur pencarian produk, filter berdasarkan kategori, manajemen keranjang,  
hingga halaman checkout produk.

---

# Fitur Aplikasi

### 1. Daftar Produk
- Menampilkan produk dalam tampilan grid
- Setiap produk menampilkan nama, harga, dan ikon produk
- Tombol tambah ke keranjang dengan notifikasi snackbar

### 2. Pencarian Produk
- Kolom pencarian berdasarkan nama produk
- Hasil filter langsung diperbarui saat pengguna mengetik

### 3. Filter Kategori
- Dropdown untuk memilih kategori produk
- Daftar kategori diambil otomatis dari data produk
- Pilihan **All** untuk menampilkan semua produk

### 4. Keranjang Belanja
- Menampilkan semua produk yang ditambahkan
- Menambah dan mengurangi jumlah item
- Otomatis menghapus item ketika quantity mencapai nol
- Menampilkan total harga secara real-time

### 5. Checkout
- Ringkasan pesanan berisi nama produk, quantity, dan subtotal
- Tombol Place Order untuk menyelesaikan pembelian
- Keranjang dikosongkan otomatis setelah order berhasil

### 6. Navigasi
- Halaman daftar produk sebagai halaman utama
- Halaman keranjang dapat diakses dari app bar
- Halaman checkout diarahkan dari halaman keranjang

---

# State Management

Aplikasi menggunakan **Provider** dengan class **CartModel** yang mengextend **ChangeNotifier**.

State yang dikelola oleh CartModel:
- Koleksi item keranjang menggunakan Map untuk lookup O(1)
- Total jumlah item dan total harga dihitung secara otomatis
- Setiap perubahan data memanggil `notifyListeners()` agar UI diperbarui secara otomatis

---

# Struktur Folder
```
lib/
│
├── models/
│   ├── product.dart
│   ├── cart_item.dart
│   └── cart_model.dart
│
├── pages/
│   ├── product_list_page.dart
│   ├── cart_page.dart
│   └── checkout_page.dart
│
└── main.dart
```

# Penjelasan Komponen

## Product
Model data produk yang menyimpan:
- id, name, price, emoji, description, category

## CartItem
Model item keranjang yang menyimpan:
- product, quantity
- properti `totalPrice` sebagai hasil perkalian harga dan quantity

## CartModel
Mengelola seluruh logika keranjang belanja:
- `addItem` — menambah produk atau menambah quantity jika sudah ada
- `removeItem` — menghapus item berdasarkan id produk
- `increaseQuantity` — menambah quantity satu item
- `decreaseQuantity` — mengurangi quantity, otomatis hapus jika mencapai nol
- `clear` — mengosongkan seluruh isi keranjang

Menggunakan **ChangeNotifier** agar setiap perubahan state langsung tercermin di UI.

---

# Teknologi yang Digunakan

- Flutter
- Dart
- Provider
- Material Design 3

---

# Tujuan Pembelajaran

Project ini dibuat untuk memahami:
- Penggunaan GridView dan ListView pada Flutter
- Navigasi antar halaman menggunakan Navigator
- Manajemen state dengan Provider dan ChangeNotifier
- Pembuatan model data dan relasi antar model
- Implementasi fitur pencarian dan filter secara dinamis
- Pengelolaan form input pada Flutter

---

# Foto Aplikasi

### Halaman Produk
> Tambahkan screenshot halaman produk di sini

### Halaman Keranjang
> Tambahkan screenshot halaman keranjang di sini

### Halaman Checkout
> Tambahkan screenshot halaman checkout di sini

---

# Author

Nama : Yudha Tri Atmaja
Program Studi : Sistem Informasi
Universitas : UNiversitas Mulawarman
