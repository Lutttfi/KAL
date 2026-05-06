# Interpretasi Geometri Sistem Persamaan Linear

Sistem persamaan linear (SPL) dengan dua variabel dapat direpresentasikan secara visual sebagai dua garis lurus pada bidang Kartesius. Memahami SPL secara geometri membantu kita memvisualisasikan mengapa sebuah sistem bisa memiliki solusi atau bahkan tidak sama sekali.

**Prinsip Dasar Geometri SPL:**
- Setiap persamaan linear membentuk **satu garis lurus**.
- Solusi dari SPL tersebut adalah **titik perpotongan** (pertemuan) dari garis-garis tersebut.

---

## 1. Sistem dengan Solusi Tunggal (Garis Berpotongan)

Sistem ini disebut juga sebagai sistem yang **konsisten dan independen**. Kedua garis memiliki gradien yang berbeda sehingga pasti akan bertemu di satu titik unik.

:::{admonition} Contoh Sistem: Solusi Tunggal
:class: tip
$$
\begin{cases}
2x + y = 5 \\
x - y = 1
\end{cases}
$$
**Hasil Aljabar:** Titik potong berada pada koordinat $(x,y) = (2,1)$.
:::

**Visualisasi Interaktif:**
Gunakan grafik di bawah ini untuk melihat bagaimana dua garis bertemu di satu titik.

<iframe src="https://www.geogebra.org/classic/qyaq2gtd?embed" width="600" height="400" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

---

## 2. Sistem Tidak Memiliki Solusi (Garis Sejajar)

Sistem ini disebut sebagai sistem yang **inkonsisten**. Secara aljabar, kedua persamaan memiliki kemiringan (gradien) yang sama tetapi memotong sumbu Y di titik yang berbeda.

:::{admonition} Contoh Sistem: Tidak Ada Solusi
:class: danger
$$
\begin{cases}
2x + y = 5 \\
2x + y = 3
\end{cases}
$$
**Interpretasi:** Karena kedua garis sejajar, mereka tidak akan pernah bertemu, sehingga tidak ada nilai $(x, y)$ yang memenuhi kedua persamaan sekaligus.
:::

**Visualisasi Interaktif:**
Perhatikan bahwa kedua garis di bawah ini selalu menjaga jarak yang sama dan tidak pernah berpotongan.

<iframe src="https://www.geogebra.org/classic/fyq9rrju?embed" width="600" height="400" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

---

## 3. Sistem Memiliki Tak Hingga Solusi (Garis Berimpit)

Sistem ini disebut sebagai sistem yang **konsisten dan dependen**. Hal ini terjadi jika satu persamaan adalah kelipatan dari persamaan lainnya.

:::{admonition} Contoh Sistem: Tak Hingga Solusi
:class: note
$$
\begin{cases}
2x + y = 5 \\
4x + 2y = 10
\end{cases}
$$
**Interpretasi:** Persamaan kedua sebenarnya adalah persamaan pertama yang dikali dua. Secara visual, kedua garis berada di posisi yang sama persis (berimpit).
:::

**Visualisasi Interaktif:**
Pada grafik di bawah, hanya terlihat satu garis karena garis kedua menumpuk tepat di atas garis pertama.

<iframe src="https://www.geogebra.org/classic/wyjc7gm3?embed" width="600" height="400" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

---

## Ringkasan Perbandingan

| Karakteristik Garis | Jumlah Solusi | Sifat Sistem |
| :--- | :--- | :--- |
| **Berpotongan** | Tepat Satu Solusi | Konsisten & Independen |
| **Sejajar** | Tidak Ada Solusi | Inkonsisten |
| **Berimpit** | Tak Hingga Solusi | Konsisten & Dependen |

:::{important}
Dalam penyelesaian menggunakan matriks (Metode Eliminasi Gaussian), sistem sejajar akan menghasilkan baris kontradiktif (misal $0 = 5$), sedangkan sistem berimpit akan menghasilkan baris nol ($0 = 0$).
:::