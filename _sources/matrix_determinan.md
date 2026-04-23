# Perhitungan Determinan (Metode Ekspansi Baris)

Sesuai dengan **Teorema 2.5.9**, determinan matriks dihitung dengan memecah matriks besar menjadi matriks yang lebih kecil (submatriks). Proses ini melibatkan tiga komponen utama: **Elemen Matriks ($a_{ik}$)**, **Tanda Kofaktor ($(-1)^{i+k}$)**, dan **Minor ($M_{ik}$)**.

---

## 1. Analisis Matriks $2 \times 2$
**Matriks:** $A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$

### Proses Penjabaran:
1. **Memilih Baris:** Kita menggunakan Baris 1 ($i=1$), yang berisi elemen $a_{11}=-7$ dan $a_{12}=-5$.
2. **Menentukan Tanda:** - Elemen $a_{11}$ berada di posisi $(1,1)$, maka tandanya $(-1)^{1+1} = +1$.
   - Elemen $a_{12}$ berada di posisi $(1,2)$, maka tandanya $(-1)^{1+2} = -1$.
3. **Mencari Minor:**
   - Untuk $M_{11}$, tutup baris 1 & kolom 1 $\rightarrow$ sisa angka **4**.
   - Untuk $M_{12}$, tutup baris 1 & kolom 2 $\rightarrow$ sisa angka **1**.



**Kalkulasi:**
$$\text{det}(A) = [(+1) \cdot (-7) \cdot (4)] + [(-1) \cdot (-5) \cdot (1)]$$
$$\text{det}(A) = -28 + 5 = \mathbf{-23}$$

---

## 2. Analisis Matriks $3 \times 3$
**Matriks:** $A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$

### Proses Penjabaran (Ekspansi Baris 1):
1. **Suku Pertama ($k=1$):**
   - Elemen $a_{11} = 0$. Karena elemen pengalinya nol, maka seluruh nilai suku ini adalah **0**, terlepas dari nilai minornya.
2. **Suku Kedua ($k=2$):**
   - Elemen $a_{12} = 2$. Tandanya negatif $(-1)^{1+2} = -1$.
   - **Minor $M_{12}$:** Tutup baris 1 & kolom 2, didapat submatriks $\begin{bmatrix} 1 & -1 \\ 0 & 1 \end{bmatrix}$.
   - Hitung determinan $2 \times 2$: $(1 \cdot 1) - (-1 \cdot 0) = 1$.
   - Hasil Suku: $(-1) \cdot (2) \cdot (1) = \mathbf{-2}$.
3. **Suku Ketiga ($k=3$):**
   - Elemen $a_{13} = -3$. Tandanya positif $(-1)^{1+3} = +1$.
   - **Minor $M_{13}$:** Tutup baris 1 & kolom 3, didapat submatriks $\begin{bmatrix} 1 & -2 \\ 0 & 0 \end{bmatrix}$.
   - Hitung determinan $2 \times 2$: $(1 \cdot 0) - (-2 \cdot 0) = 0$.
   - Hasil Suku: $(+1) \cdot (-3) \cdot (0) = \mathbf{0}$.



**Hasil Akhir:**
$$\text{det}(A) = 0 + (-2) + 0 = \mathbf{-2}$$

---

## 3. Analisis Matriks $4 \times 4$
**Matriks:** $A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$

### Proses Penjabaran (Metode Rekursif):
Untuk matriks $4 \times 4$, prosesnya lebih panjang karena setiap minornya adalah matriks $3 \times 3$.

1. **Pemecahan Masalah:** Baris 1 mengandung angka $1, -3, 1, 1$. Kita harus mencari 4 determinan matriks $3 \times 3$.
2. **Distribusi Tanda:** Pola tanda baris pertama adalah $(+, -, +, -)$.
3. **Eksekusi Suku:**
   - **Suku 1:** $(+1)(1) \cdot \text{det}(M_{11})$. Setelah dihitung, $\text{det}(M_{11}) = 16$. Maka $1 \cdot 16 = \mathbf{16}$.
   - **Suku 2:** $(-1)(-3) \cdot \text{det}(M_{12})$. Setelah dihitung, $\text{det}(M_{12}) = -16$. Maka $(3) \cdot (-16) = \mathbf{-48}$.
   - **Suku 3:** $(+1)(1) \cdot \text{det}(M_{13})$. Setelah dihitung, $\text{det}(M_{13}) = 16$. Maka $1 \cdot 16 = \mathbf{16}$.
   - **Suku 4:** $(-1)(1) \cdot \text{det}(M_{14})$. Setelah dihitung, $\text{det}(M_{14}) = -16$. Maka $(-1) \cdot (-16) = \mathbf{16}$.




### Kalkulasi Akhir:
$$\text{det}(A) = 16 - 48 + 16 + 16$$
$$\text{det}(A) = \mathbf{0}$$

**Interpretasi Hasil:**
Hasil determinan **0** menunjukkan bahwa matriks ini adalah **matriks singular**. Dalam konteks sistem persamaan linear, ini berarti sistem tersebut tidak memiliki solusi unik atau memiliki solusi tak hingga.