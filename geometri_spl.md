# Interpretasi Geometri Sistem Persamaan Linear

Sistem persamaan linear (SPL) dengan dua variabel dapat direpresentasikan secara visual sebagai dua garis lurus pada bidang Kartesius.

Secara geometri, prinsip dasarnya adalah:

- Setiap persamaan linear membentuk **satu garis lurus**.
- Solusi dari SPL tersebut adalah **titik perpotongan** dari garis-garis tersebut.

---

## 1. Sistem dengan Solusi Tunggal (Garis Berpotongan)

**Contoh Sistem:**

$$
\begin{cases}
2x + y = 5 \\
x - y = 1
\end{cases}
$$

**Interpretasi:**
Kedua persamaan membentuk dua garis yang saling berpotongan. Titik potong dari kedua garis inilah yang merupakan solusi dari sistem tersebut. Dengan perhitungan, diperoleh titik potong pada koordinat:

$$(x,y) = (2,1)$$

**Visualisasi GeoGebra:**

<iframe src="https://www.geogebra.org/classic/tgazqzgd?embed" width="600" height="400" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

> **Catatan:** Dari grafik terlihat jelas bahwa kedua garis berpotongan tepat di titik (2,1), sehingga sistem ini memiliki **satu solusi**.

---

## 2. Sistem Tidak Memiliki Solusi (Garis Sejajar)

**Contoh Sistem:**

$$
\begin{cases}
2x + y = 5 \\
2x + y = 3
\end{cases}
$$

**Interpretasi:**
Kedua persamaan memiliki gradien (kemiringan) yang sama, namun nilai konstantanya berbeda. Artinya, kedua garis tersebut sejajar dan tidak akan pernah berpotongan sampai kapan pun. Karena tidak ada titik temu, maka sistem ini **tidak memiliki solusi**.

**Visualisasi GeoGebra:**

<iframe src="https://www.geogebra.org/classic/fyq9rrju?embed" width="600" height="400" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

> **Catatan:** Terlihat bahwa kedua garis berjalan sejajar berdampingan, maka dipastikan tidak ada titik potong.

---

## 3. Sistem Memiliki Tak Hingga Solusi (Garis Berimpit)

**Contoh Sistem:**

$$
\begin{cases}
2x + y = 5 \\
4x + 2y = 10
\end{cases}
$$

**Interpretasi:**
Jika diperhatikan, persamaan kedua pada dasarnya hanyalah kelipatan (dikali dua) dari persamaan pertama. Secara geometri, kedua persamaan ini merepresentasikan garis lurus yang persis sama. Artinya, garis tersebut saling menumpuk atau berimpit, sehingga **setiap titik** di sepanjang garis tersebut adalah solusi. Sistem ini memiliki **tak hingga solusi**.

**Visualisasi GeoGebra:**

<iframe src="https://www.geogebra.org/classic/wyjc7gm3?embed" width="600" height="400" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

> **Catatan:** Grafik menunjukkan kedua persamaan menghasilkan satu garis yang sama, sehingga semua titik pada garis tersebut memenuhi kedua persamaan.

---

## Kesimpulan Geometri SPL

Sebagai ringkasan, interpretasi geometri membantu kita memahami hubungan antara perhitungan aljabar dan representasi grafisnya. Sistem persamaan linear dua variabel selalu memiliki satu dari tiga kemungkinan berikut:

1. **Garis Berpotongan** $\rightarrow$ Memiliki tepat satu solusi.
2. **Garis Sejajar** $\rightarrow$ Tidak memiliki solusi sama sekali.
3. **Garis Berimpit** $\rightarrow$ Memiliki tak hingga solusi.

---
