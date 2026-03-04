# Eliminasi Gaussian

**Eliminasi Gaussian** adalah algoritma sistematis untuk mengubah matriks menjadi **Bentuk Eselon Baris (Row Echelon Form)**. Metode ini mempermudah kita dalam menyelesaikan Sistem Persamaan Linear (SPL) yang kompleks dengan cara menyederhanakan matriks melalui serangkaian operasi baris elemen-ter.

### Tujuan Utama

- Mendefinisikan sistem yang lebih sederhana untuk dipecahkan.
- Memberikan algoritma langkah-demi-langkah yang jelas.
- Memudahkan pembacaan solusi melalui substitusi balik.

---

### Contoh Operasi Baris dan Eliminasi

Diberikan sistem persamaan berikut:

$$
\begin{cases}
x_1 - x_2 + x_3 = 3 \\
2x_1 + x_2 + 8x_3 = 18 \\
4x_1 + 2x_2 - 3x_3 = -2
\end{cases}
$$

Kita akan menggunakan tiga operasi baris dasar untuk menyederhanakannya:

1.  **Rescale Row**: Mengalikan baris dengan angka bukan nol.
2.  **Add Multiple of Row**: Menambahkan kelipatan satu baris ke baris lain.
3.  **Swap Rows**: Menukar posisi dua baris.

#### Implementasi Kode (Python)

Gunakan fungsi baris pada objek matriks untuk melakukan transformasi:

```python
# Inisialisasi Matriks Augmented
A = matrix([[1, -1, 1, 3], [2, 1, 8, 18], [4, 2, -3, -2]])

# 1. Buat nol di bawah pivot baris pertama
A.add_multiple_of_row(1, 0, -2) # Baris 1 = Baris 1 + (-2 * Baris 0)
A.add_multiple_of_row(2, 0, -4) # Baris 2 = Baris 2 + (-4 * Baris 0)

# 2. Buat nol di bawah pivot baris kedua
A.add_multiple_of_row(2, 1, -2) # Baris 2 = Baris 2 + (-2 * Baris 1)

# 3. Normalisasi pivot (Rescale agar nilai utama menjadi 1)
A.rescale_row(1, 1/3)
A.rescale_row(2, -1/19)
```
