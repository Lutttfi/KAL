# Penyelesaian SPL dengan Operasi Baris Elementer (OBE)

## 1. Aturan Dasar Operasi Baris Elementer

Dalam menyelesaikan matriks augmented, terdapat tiga jenis Operasi Baris Elementer (OBE) yang sah untuk dilakukan:

1. **Menukar** posisi dua baris.
2. **Mengalikan** suatu baris dengan konstanta bukan nol.
3. **Menambahkan** kelipatan suatu baris ke baris lainnya.

---

## 2. Contoh Soal dan Pembahasan

Diberikan Sistem Persamaan Linear (SPL) berikut:

$$
\begin{cases}
2x + y = 5 \\
x - y = 1
\end{cases}
$$

### Bentuk Matriks Augmented

Ubah SPL di atas menjadi bentuk matriks diperbesar (augmented matrix):

$$
\left[
\begin{array}{cc|c}
2 & 1 & 5 \\
1 & -1 & 1
\end{array}
\right]
$$

### Langkah Eliminasi (Menuju Bentuk Eselon Baris)

**Langkah 1:** Membuat angka nol di bawah pivot baris pertama (kolom pertama, baris kedua).

- **Operasi:** $R_2 \rightarrow R_2 - \frac{1}{2}R_1$
- **Hasil:**

$$
\left[
\begin{array}{cc|c}
2 & 1 & 5 \\
0 & -\frac{3}{2} & -\frac{3}{2}
\end{array}
\right]
$$

**Langkah 2 (Koreksi):** Menyederhanakan baris kedua agar koefisien utama menjadi 1.

- **Operasi:** $R_2 \rightarrow -\frac{2}{3}R_2$
- **Hasil:**

$$
\left[
\begin{array}{cc|c}
2 & 1 & 5 \\
0 & 1 & 1
\end{array}
\right]
$$

### Substitusi Balik

Dari matriks hasil eliminasi di Langkah 2, kita dapat langsung membaca nilai $y$:

$$y = 1$$

Substitusikan nilai $y$ ke persamaan dari baris pertama ($2x + y = 5$):

$$2x + 1 = 5$$

$$2x = 4$$

$$x = 2$$

### Hasil Akhir

Himpunan penyelesaian untuk sistem persamaan linear tersebut adalah:

$$(x, y) = (2, 1)$$

---

## 3. Implementasi Eliminasi Gauss dengan Python

Kamu juga bisa menggunakan kode Python berikut dengan memanfaatkan _library_ NumPy untuk menghitung penyelesaian matriks secara otomatis:

```python
import numpy as np

def eliminasi_gauss(A):
    # Memastikan tipe data float agar pembagian akurat
    A = A.astype(float)
    n = len(A)

    for i in range(n):
        # Pivoting parsial: Tukar baris jika pivot bernilai 0
        if A[i][i] == 0:
            for j in range(i+1, n):
                if A[j][i] != 0:
                    A[[i, j]] = A[[j, i]]
                    break

        # Buat nilai pivot menjadi 1
        pivot = A[i][i]
        A[i] = A[i] / pivot

        # Eliminasi baris di bawah pivot agar menjadi 0
        for j in range(i+1, n):
            faktor = A[j][i]
            A[j] = A[j] - faktor * A[i]

    return A

def gauss_solve(A):
    # Lakukan eliminasi maju
    A = eliminasi_gauss(A)
    n = len(A)
    x = np.zeros(n)

    # Lakukan substitusi mundur (back substitution)
    for i in range(n-1, -1, -1):
        x[i] = A[i][-1] - np.dot(A[i][i+1:n], x[i+1:n])

    return x

# Definisikan matriks augmented dari soal
A = np.array([[2., 1., 5.],
              [1., -1., 1.]])

solusi = gauss_solve(A)

print("Solusi SPL:")
print(f"x = {solusi[0]:.0f}")
print(f"y = {solusi[1]:.0f}")

```

---
