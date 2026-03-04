# Konsep Dasar Sistem Persamaan Linear

## Definisi

Sistem Persamaan Linear (SPL) adalah sekumpulan persamaan linear
yang memiliki variabel yang sama.

Bentuk umum SPL dua variabel:

$$
\begin{cases}
a_1x + b_1y = c_1 \\
a_2x + b_2y = c_2
\end{cases}
$$

dengan:

- \(a_1, a_2, b_1, b_2\) adalah koefisien
- \(x, y\) adalah variabel
- \(c_1, c_2\) adalah konstanta

---

## Bentuk Matriks

SPL dapat ditulis dalam bentuk matriks:

\[
AX = B
\]

dengan:

$$
A =
\begin{bmatrix}
a_1 & b_1 \\
a_2 & b_2
\end{bmatrix}
\quad
X =
\begin{bmatrix}
x \\
y
\end{bmatrix}
\quad
B =
\begin{bmatrix}
c_1 \\
c_2
\end{bmatrix}
$$

---

## Matriks Augmented

Matriks augmented adalah penggabungan matriks koefisien dan konstanta:

$$
\left[
\begin{array}{cc|c}
a_1 & b_1 & c_1 \\
a_2 & b_2 & c_2
\end{array}
\right]
$$

---

## Jenis Solusi SPL

1. Solusi Tunggal  
   Jika determinan matriks koefisien ≠ 0

2. Tak Hingga Solusi  
   Jika kedua persamaan saling kelipatan

3. Tidak Ada Solusi  
   Jika garis sejajar
