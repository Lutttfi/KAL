# Invers Matriks & Metode Adjoint

Berdasarkan rumus yang diberikan, invers matriks $A$ dapat ditentukan dengan mencari matriks adjoint dan membaginya dengan determinan:

$$(adj \ A)_{ij} = (-1)^{i+j} M_{ji}$$
$$A^{-1} = \frac{1}{\det A} adj \ A$$

---

## 4. Matriks $2 \times 2$
**Matriks:** $A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$

### Langkah-langkah Penyelesaian:

1. **Hitung Determinan ($\det A$):**
   $$\det A = (-7 \cdot 4) - (-5 \cdot 1) = -28 + 5 = \mathbf{-23}$$
   
2. **Cari Matriks Kofaktor ($C$):**
   - $C_{11} = (-1)^{1+1} (4) = 4$
   - $C_{12} = (-1)^{1+2} (1) = -1$
   - $C_{21} = (-1)^{2+1} (-5) = 5$
   - $C_{22} = (-1)^{2+2} (-7) = -7$
   
3. **Tentukan Adjoint ($adj \ A$):**
   Adjoint adalah transpose dari matriks kofaktor.
   $$adj \ A = \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix}$$

4. **Hitung Invers ($A^{-1}$):**
   $$A^{-1} = \frac{1}{-23} \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix} = \begin{bmatrix} -4/23 & -5/23 \\ 1/23 & 7/23 \end{bmatrix}$$

---

## 5. Matriks $3 \times 3$
**Matriks:** $A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$

### Langkah-langkah Penyelesaian:

1. **Hitung Determinan ($\det A$):**
   Menggunakan ekspansi baris ke-3 (karena memiliki angka nol terbanyak):
   $$\det A = 0 + 0 + 1 \cdot \begin{vmatrix} 0 & 2 \\ 1 & -2 \end{vmatrix} = 1(0 - 2) = \mathbf{-2}$$

2. **Cari Matriks Kofaktor ($C$):**
      - $C_{11} = +|(-2)(1) - (-1)(0)| = -2$
   - $C_{12} = -|(1)(1) - (-1)(0)| = -1$
   - $C_{13} = +|(1)(0) - (-2)(0)| = 0$
   - $C_{21} = -|(2)(1) - (-3)(0)| = -2$
   - $C_{22} = +|(0)(1) - (-3)(0)| = 0$
   - $C_{23} = -|(0)(0) - (2)(0)| = 0$
   - $C_{31} = +|(2)(-1) - (-3)(-2)| = -8$
   - $C_{32} = -|(0)(-1) - (-3)(1)| = -3$
   - $C_{33} = +|(0)(-2) - (2)(1)| = -2$

3. **Tentukan Adjoint ($adj \ A$):**
   Transpose matriks kofaktor ($C^T$):
   $$adj \ A = \begin{bmatrix} -2 & -2 & -8 \\ -1 & 0 & -3 \\ 0 & 0 & -2 \end{bmatrix}$$

4. **Hitung Invers ($A^{-1}$):**
   $$A^{-1} = \frac{1}{-2} \begin{bmatrix} -2 & -2 & -8 \\ -1 & 0 & -3 \\ 0 & 0 & -2 \end{bmatrix} = \begin{bmatrix} 1 & 1 & 4 \\ 0.5 & 0 & 1.5 \\ 0 & 0 & 1 \end{bmatrix}$$

---

## 6. Matriks $4 \times 4$
**Matriks:** $A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$

### Langkah-langkah Penyelesaian:

1. **Hitung Determinan ($\det A$):**
   Berdasarkan perhitungan pada bab sebelumnya (Metode Ekspansi Baris), diperoleh hasil:
   $$\det A = \mathbf{0}$$

2. **Analisis Matriks Singular:**
   Karena nilai determinan adalah **nol**, matriks ini dikategorikan sebagai **Matriks Singular**. 
   - Syarat utama sebuah matriks memiliki invers adalah $\det A \neq 0$.
   - **Kesimpulan:** Invers matriks $A$ **tidak ada** (tidak terdefinisi). Proses perhitungan Adjoint untuk mencari invers tidak dapat dilanjutkan.

---
**Catatan Penting:** Dalam dunia pemrograman, sangat krusial untuk melakukan pengecekan nilai determinan terlebih dahulu sebelum melakukan operasi invers untuk menghindari error pembagian dengan nol.