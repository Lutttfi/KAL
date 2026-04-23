# Konsep Dasar Sistem Persamaan Linear (SPL)

Sistem Persamaan Linear (SPL) adalah sekumpulan persamaan linear yang saling terkait dan memiliki variabel yang sama. Memahami struktur SPL adalah langkah awal yang krusial dalam Aljabar Linear.

---

## 1. Bentuk Umum

Secara matematis, SPL dengan dua variabel dapat dituliskan sebagai berikut:

$$
\begin{cases}
a_1x + b_1y = c_1 \\
a_2x + b_2y = c_2
\end{cases}
$$

:::{admonition} Deskripsi Komponen
* **$a_1, a_2, b_1, b_2$**: merupakan **Koefisien** (angka yang menyertai variabel).
* **$x, y$**: merupakan **Variabel** (nilai yang ingin dicari solusinya).
* **$c_1, c_2$**: merupakan **Konstanta** (nilai tetap di ruas kanan persamaan).
:::

---

## 2. Representasi Matriks

Untuk mempermudah komputasi dan perhitungan, sebuah SPL dapat direpresentasikan secara ringkas dalam bentuk persamaan matriks:

$$\mathbf{AX = B}$$

**Detail Elemen Matriks:**

$$
A = \begin{bmatrix} a_1 & b_1 \\ a_2 & b_2 \end{bmatrix}, \quad 
X = \begin{bmatrix} x \\ y \end{bmatrix}, \quad 
B = \begin{bmatrix} c_1 \\ c_2 \end{bmatrix}
$$



---

## 3. Matriks Augmented

Matriks *augmented* (matriks diperbesar) digunakan untuk menyederhanakan proses eliminasi (seperti Eliminasi Gauss). Matriks ini menggabungkan matriks koefisien dengan matriks konstanta ke dalam satu struktur:

$$
\left[
\begin{array}{cc|c}
a_1 & b_1 & c_1 \\
a_2 & b_2 & c_2
\end{array}
\right]
$$

:::{tip}
Garis vertikal $|$ di dalam matriks tersebut secara visual memisahkan sisi kiri (koefisien variabel) dengan sisi kanan (hasil konstanta).
:::

---

## 4. Analisis Solusi SPL

Solusi dari SPL dua variabel dapat dianalisis baik secara aljabar (melalui determinan) maupun secara geometri (melalui grafik garis).

| Jenis Solusi | Kondisi Aljabar | Interpretasi Geometri |
| :--- | :--- | :--- |
| **Solusi Tunggal** | Determinan $A \neq 0$ | Garis-garis saling **berpotongan** di satu titik. |
| **Tak Hingga Solusi** | Persamaan saling **kelipatan** | Garis-garis saling **berimpit** (satu lintasan). |
| **Tidak Ada Solusi** | Persamaan **inkonsisten** | Garis-garis saling **sejajar** (tidak ada titik temu). |



---