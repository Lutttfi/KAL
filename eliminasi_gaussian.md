# Eliminasi Gaussian dengan SageMath

Eliminasi Gaussian adalah prosedur algoritmik dalam aljabar linear untuk mengubah matriks augmented menjadi bentuk **Eselon Baris**. Proses ini menggunakan Operasi Baris Elementer (OBE) untuk menyederhanakan sistem sehingga solusi dapat ditemukan dengan mudah.

---

## 1. Penyelesaian SPL Tiga Variabel

Diberikan Sistem Persamaan Linear (SPL) berikut:

$$
\begin{cases}
2x + y - z = 8 \\
-3x - y + 2z = -11 \\
-2x + y + 2z = -3
\end{cases}
$$

### Langkah 1: Inisialisasi Matriks Augmented
Langkah pertama adalah menyusun koefisien dan konstanta ke dalam matriks. Kita menggunakan ring `QQ` agar hasil perhitungan tetap dalam bentuk pecahan (bukan desimal) untuk menjaga akurasi.

```python
M1 = matrix(QQ, [[2, 1, -1, 8], 
                 [-3, -1, 2, -11], 
                 [-2, 1, 2, -3]])
show(M1)
```

### Langkah 2: Menentukan Pivot Pertama
Kita perlu membuat angka 1 (pivot) pada baris pertama kolom pertama.
Operasi: Baris ke-0 dikalikan dengan $1/2$ ($R_0 \leftarrow \frac{1}{2} R_0$).
```python
M1.rescale_row(0, 1/2)
show(M1)
```

### Langkah 3: Eliminasi Kolom Pertama
Setelah pivot terbentuk, kita nolkan semua angka di bawah pivot tersebut pada kolom ke-0.
Operasi: $R_1 \leftarrow 3R_0 + R_1$ dan $R_2 \leftarrow 2R_0 + R_2$.
```python
M1.add_multiple_of_row(1, 0, 3) 
M1.add_multiple_of_row(2, 0, 2)
show(M1)
```

### Langkah 4: Menentukan Pivot Kedua
Kita berpindah ke baris kedua kolom kedua untuk membuat pivot bernilai 1.
Operasi: Baris ke-1 dikalikan dengan $2$ ($R_1 \leftarrow 2 R_1$).
```python
M1.rescale_row(1, 2)
show(M1)
```

### Langkah 5: Eliminasi Kolom Kedua
Nolkan angka di bawah pivot kedua pada kolom ke-1.
Operasi: $R_2 \leftarrow -2R_1 + R_2$.
```python
M1.add_multiple_of_row(2, 1, -2)
show(M1)
```

### Langkah 6: Menentukan Pivot Ketiga
Terakhir, buat pivot bernilai 1 pada baris ketiga kolom ketiga.
Operasi: Baris ke-2 dikalikan dengan $-1$ ($R_2 \leftarrow -1 R_2$).
```python
M1.rescale_row(2, -1)
show(M1)
```

## 2. Penyelesaian SPL Empat Variabel

Diberikan SPL empat variabel:

$$
\begin{cases}
w + x + y + z = 10 \\
2w + 3x + y - z = 7 \\
3w + 2x + 2y + z = 17 \\
4w + x - y + 2z = 10
\end{cases}
$$

### Langkah 1: Representasi Matriks 4x5
Memasukkan seluruh data persamaan ke dalam matriks augmented berukuran $4 \times 5$.
```python
M2 = matrix(QQ, [
    [1, 1, 1, 1, 10],
    [2, 3, 1, -1, 7],
    [3, 2, 2, 1, 17],
    [4, 1, -1, 2, 10]
])
show(M2)
```

### Langkah 2: Eliminasi Kolom Pertama

Karena pivot pada baris pertama sudah bernilai 1, kita langsung menolkan elemen di bawahnya.
Operasi: Kurangi baris-baris di bawahnya dengan kelipatan baris ke-0.
```python
M2.add_multiple_of_row(1, 0, -2)
M2.add_multiple_of_row(2, 0, -3)
M2.add_multiple_of_row(3, 0, -4)
show(M2)
```

### Langkah 3: Eliminasi Kolom Kedua
Lanjutkan proses nolkan elemen di bawah pivot baris ke-1.
Operasi: $R_2 \leftarrow 1R_1 + R_2$ dan $R_3 \leftarrow 3R_1 + R_3$.
```python
M2.add_multiple_of_row(2, 1, 1)
M2.add_multiple_of_row(3, 1, 3)
show(M2)
```

### Langkah 4: Pivot Baris Ketiga dan Eliminasi
Membuat pivot pada baris ke-2 menjadi 1, lalu menolkan baris di bawahnya.
Operasi: $R_2 \leftarrow -1/2 R_2$ kemudian $R_3 \leftarrow 8R_2 + R_3$
```python
M2.rescale_row(2, -1/2)
M2.add_multiple_of_row(3, 2, 8)
show(M2)
```

### Langkah 5: Finalisasi Bentuk Eselon
Langkah terakhir adalah membuat pivot baris ke-3 menjadi 1.
Operasi: $R_3 \leftarrow -1/6 R_3$.
```python
M2.rescale_row(3, -1/6)
print("Matriks Hasil Akhir (Eselon Baris):")
show(M2)
```