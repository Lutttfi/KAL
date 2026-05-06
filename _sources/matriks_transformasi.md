# Matriks Transformasi Geometri

Transformasi linear adalah pemetaan yang memindahkan titik-titik pada bidang koordinat menggunakan operasi perkalian matriks. Dalam sistem koordinat 2D, sebuah titik atau vektor $\vec{v} = (x, y)$ diubah menjadi titik baru $\vec{v'} = (x', y')$ melalui perkalian dengan matriks transformasi $A$.

$$
\begin{bmatrix} x' \\ y' \end{bmatrix} = \begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix}
$$

## 1. Jenis-Jenis Matriks Transformasi Dasar

Berikut adalah daftar matriks standar yang digunakan untuk berbagai jenis transformasi geometri:

| Jenis Transformasi | Matriks Standar ($A$) | Deskripsi |
| :--- | :---: | :--- |
| **Scaling** (Skala) | $\begin{bmatrix} s_x & 0 \\ 0 & s_y \end{bmatrix}$ | Mengubah ukuran objek berdasarkan faktor $s_x$ dan $s_y$. |
| **Rotation** (Rotasi) | $\begin{bmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{bmatrix}$ | Memutar objek sebesar sudut $\theta$ terhadap titik asal. |
| **Shearing** (Geseran) | $\begin{bmatrix} 1 & k \\ 0 & 1 \end{bmatrix}$ | Menarik objek ke arah samping (kemiringan). |
| **Reflection** (Refleksi) | $\begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$ | Mencerminkan objek terhadap sumbu X. |

---

## 2. Visualisasi Interaktif GeoGebra

Gunakan alat interaktif di bawah ini untuk melihat bagaimana matriks transformasi mengubah bentuk objek secara langsung. Kamu bisa menggeser titik-titik yang ada untuk melihat perubahan koordinatnya.

<iframe src="https://www.geogebra.org/material/iframe/id/vze78f8v/width/800/height/500/ai/false/sc/false/sbm/false/sbc/false/lp/false/li/false" 
        width="100%" 
        height="500px" 
        style="border: 1px solid #e4e4e4; border-radius: 8px;">
</iframe>

---

## 3. Implementasi dengan Python

Berikut adalah contoh cara menghitung hasil rotasi titik menggunakan pustaka `numpy`.

:::{admonition} Contoh Kasus
:class: tip
Hitunglah bayangan titik $A(2, 3)$ setelah dirotasi $90^\circ$ berlawanan arah jarum jam!
:::

```python
import numpy as np

# 1. Definisi koordinat titik A
A = np.array([2, 3])

# 2. Membuat Matriks Rotasi 90 derajat
theta = np.radians(90)
R = np.array([[np.cos(theta), -np.sin(theta)],
              [np.sin(theta),  np.cos(theta)]])

# 3. Hitung hasil transformasi (A' = R . A)
A_aksen = R.dot(A)

print(f"Hasil Rotasi Titik A adalah: {A_aksen}")