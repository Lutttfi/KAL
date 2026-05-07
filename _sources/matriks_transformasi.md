# Matriks Transformasi Linear

Dalam Aljabar Linear, sebuah transformasi $T: \mathbb{R}^n \to \mathbb{R}^m$ disebut **transformasi linear** jika pemetaan tersebut dapat direpresentasikan dalam bentuk perkalian matriks. Untuk setiap vektor $\mathbf{x}$, transformasinya dapat dituliskan sebagai:

$$T(\mathbf{x}) = A\mathbf{x}$$

Di mana $A$ adalah **matriks standar** untuk transformasi tersebut.



## 1. Konsep Dasar Transformasi 2D

Secara geometris, transformasi ini mengubah posisi titik asal $(x, y)$ menjadi koordinat baru $(x', y')$. Hubungan ini dinyatakan dalam sistem persamaan linear yang dipadatkan ke dalam bentuk matriks:

$$\begin{bmatrix} x' \\ y' \end{bmatrix} = \begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix}$$

### Tabel Referensi Matriks Transformasi Standar

| Jenis Transformasi | Matriks Standar ($A$) | Penjelasan Geometris |
| :--- | :---: | :--- |
| **Refleksi (Sumbu X)** | $\begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$ | Mencerminkan objek terhadap garis horizontal $y=0$. |
| **Refleksi (Sumbu Y)** | $\begin{bmatrix} -1 & 0 \\ 0 & 1 \end{bmatrix}$ | Mencerminkan objek terhadap garis vertikal $x=0$. |
| **Scaling (Skala)** | $\begin{bmatrix} s_x & 0 \\ 0 & s_y \end{bmatrix}$ | Mengubah ukuran objek dengan faktor $s_x$ dan $s_y$. |
| **Shear (Sumbu X)** | $\begin{bmatrix} 1 & k \\ 0 & 1 \end{bmatrix}$ | Menggeser bagian atas objek sejauh $k$ secara horizontal. |
| **Rotasi ($\theta$)** | $\begin{bmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{bmatrix}$ | Memutar objek sejauh $\theta$ berlawanan arah jarum jam. |



---

## 2. Visualisasi Interaktif GeoGebra

Gunakan simulasi di bawah ini untuk melihat bagaimana perubahan nilai pada elemen matriks mempengaruhi vektor unit di bidang Cartesian secara *real-time*.

<iframe src="https://www.geogebra.org/classic/pf3xmaqw?embed" width="600" height="400" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

---

## 3. Komposisi Transformasi (Transformasi Berurutan)

Jika sebuah objek mengalami beberapa transformasi secara berturut-turut, kita dapat menggabungkannya menjadi satu matriks tunggal. Misalnya, jika objek ditransformasi oleh matriks $A$, kemudian dilanjutkan dengan matriks $B$, maka matriks totalnya adalah:

$$A_{total} = B \cdot A$$

**Penting:** Urutan perkalian matriks dilakukan dari kanan ke kiri (transformasi yang dilakukan pertama berada di posisi paling kanan).

---

## 4. Contoh Soal dan Penyelesaian

:::{admonition} Contoh 1: Rotasi Titik
:class: tip
Tentukan koordinat bayangan titik $P(4, 2)$ setelah dirotasi sebesar $90^\circ$ berlawanan arah jarum jam terhadap titik asal $(0,0)$.
:::

**Penyelesaian:**
1. **Matriks Rotasi $90^\circ$ ($R$):**
   Karena $\cos 90^\circ = 0$ dan $\sin 90^\circ = 1$, maka:
   $$R = \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$$

2. **Perkalian Matriks:**
   $$\begin{bmatrix} x' \\ y' \end{bmatrix} = \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \begin{bmatrix} 4 \\ 2 \end{bmatrix} = \begin{bmatrix} (0 \cdot 4) + (-1 \cdot 2) \\ (1 \cdot 4) + (0 \cdot 2) \end{bmatrix} = \begin{bmatrix} -2 \\ 4 \end{bmatrix}$$

**Hasil:** Bayangan titik $P$ adalah **$(-2, 4)$**.

---

:::{admonition} Contoh 2: Transformasi Komposit
:class: warning
Sebuah objek pertama-tama direfleksikan terhadap sumbu Y, kemudian diskalakan dengan faktor $s_x = 2$ dan $s_y = 2$. Cari matriks transformasinya!
:::

**Penyelesaian:**
1. Matriks Refleksi Sumbu Y ($M$): $\begin{bmatrix} -1 & 0 \\ 0 & 1 \end{bmatrix}$
2. Matriks Skala ($S$): $\begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix}$
3. Matriks Gabungan ($A = S \cdot M$):
   $$A = \begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix} \begin{bmatrix} -1 & 0 \\ 0 & 1 \end{bmatrix} = \begin{bmatrix} -2 & 0 \\ 0 & 2 \end{bmatrix}$$

---

## 5. Implementasi Komputasi (Python)

```python
import numpy as np

# Definisi vektor posisi
v = np.array([4, 2])

# Matriks Rotasi 90 derajat
R = np.array([[0, -1], 
              [1,  0]])

# Menghitung hasil transformasi (dot product)
v_prime = R @ v

print(f"Vektor awal: {v}")
print(f"Vektor hasil transformasi: {v_prime}")

# Tutorial Membuat Animasi Refleksi Matematika

Berikut adalah kode Python menggunakan Matplotlib untuk membuat kotak yang bergerak naik turun, beserta bayangannya di cermin:

```python
import matplotlib.pyplot as plt
import matplotlib.animation as animation
import numpy as np

# Inisialisasi Figure
fig, ax = plt.subplots(figsize=(6, 8))

# Titik koordinat persegi ABCD
x_obj = np.array([2, 2, 3, 3, 2])
y_obj_base = np.array([3, 4, 4, 3, 3])

# Cermin DIAM di sumbu X (y = 0)
mirror_y = 0

# ... (tulis sisa kodenya di sini) ...
```

Dan ini adalah hasil output animasinya:

<!-- Kalau kamu pakai format GIF -->
![Hasil Animasi Refleksi](/path/ke/folder/animasi_refleksi.gif)

<!-- ATAU, kalau kamu pakai format HTML Widget Interaktif -->
<iframe src="/path/ke/folder/animasi_widget.html" width="100%" height="650" frameborder="0"></iframe>