# Sistem Inferensi Fuzzy dengan Python (scikit-fuzzy)
Repositori ini berisi dua implementasi sistem inferensi fuzzy menggunakan library `scikit-fuzzy` pada Python.

## Struktur Program
├── stok_makanan.py        # Program 1: Rekomendasi stok makanan
├── kepuasan_pelayanan.py  # Program 2: Evaluasi kepuasan pelayanan
└── README.md

## Requirement
Pastikan Python dan library berikut sudah terinstal:
pip install numpy scikit-fuzzy matplotlib

## Program 1 - Rekomendasi Stok Makanan
### Deskripsi
Program ini menggunakan logika fuzzy untuk menentukan jumlah stok makanan yang direkomendasikan berdasarkan data penjualan.

### Variabel Input
| Variabel       | Rentang       | Himpunan Fuzzy         |
|----------------|---------------|------------------------|
| Barang Terjual | 0 - 100       | Rendah, Sedang, Tinggi |
| Permintaan     | 0 - 300       | Rendah, Sedang, Tinggi |
| Harga per Item | 0 - 100.000   | Murah, Sedang, Mahal   |
| Profit         | 0 - 4.000.000 | Rendah, Sedang, Banyak |
|----------------|---------------|------------------------|

### Variabel Output
|--------------|----------|----------------|
| Variabel     | Rentang  | Himpunan Fuzzy |
|--------------|----------|----------------|
| Stok Makanan | 0 - 1000 | Sedang, Banyak |
|--------------|----------|----------------|

### Jumlah Aturan
6 aturan fuzzy (IF-THEN)

### Contoh Input dan Output
Barang Terjual : 80
Permintaan     : 255
Harga per Item : 25000
Profit         : 3500000
-------------------------------
Output: Jumlah Stok Makanan yang Direkomendasikan: ... unit

### Cara Menjalankan
python stok_makanan.py

## Program 2 - Evaluasi Kepuasan Pelayanan
### Deskripsi
Program ini menggunakan logika fuzzy untuk mengevaluasi tingkat kepuasan pelayanan berdasarkan empat aspek penilaian.

### Variabel Input
|-----------------------|---------|---------------------------------------------|
| Variabel              | Rentang | Himpunan Fuzzy                              |
|-----------------------|---------|---------------------------------------------|
| Kejelasan Informasi   | 0 - 100 | Tidak Memuaskan, Cukup Memuaskan, Memuaskan |
| Kejelasan Persyaratan | 0 - 100 | Tidak Memuaskan, Cukup Memuaskan, Memuaskan |
| Kemampuan Petugas     | 0 - 100 | Tidak Memuaskan, Cukup Memuaskan, Memuaskan |
| Ketersediaan Sarpras  | 0 - 100 | Tidak Memuaskan, Cukup Memuaskan, Memuaskan |
|-----------------------|---------|---------------------------------------------|

### Variabel Output
| Variabel           | Rentang | Himpunan Fuzzy                                                                  |
| Kepuasan Pelayanan | 0 - 400 | Tidak Memuaskan, Kurang Memuaskan, Cukup Memuaskan, Memuaskan, Sangat Memuaskan |

### Jumlah Aturan
81 aturan fuzzy (3 pangkat 4 kombinasi lengkap)

### Contoh Input dan Output
Kejelasan Informasi   : 80
Kejelasan Persyaratan : 60
Kemampuan Petugas     : 50
Ketersediaan Sarpras  : 90
-------------------------------
Output: Skor Kepuasan Pelayanan: ...

### Cara Menjalankan
python pelayanan_masyarakat.py

## Alur Kerja Sistem
Input Nilai --> Fuzzifikasi --> Evaluasi Aturan --> Defuzzifikasi --> Output
1. Fuzzifikasi — Nilai tegas diubah menjadi derajat keanggotaan pada setiap himpunan fuzzy
2. Evaluasi Aturan — Seluruh aturan IF-THEN dievaluasi secara bersamaan menggunakan operator AND
3. Defuzzifikasi — Hasil fuzzy dikonversi kembali menjadi nilai tegas menggunakan metode centroid
