## _Eliminasi Gaussian_

Eliminasi Gaussian adalah algoritma untuk mengubah matriks menjadi bentuk eselon baris (REF). Bagian ini melengkapi pembahasan sistem persamaan linear dengan memberikan metode sistematis untuk menyederhanakan dan menyelesaikannya menggunakan matriks dan operasi baris.

Tujuan utama:

1. Mendefinisikan secara tepat apa yang dimaksud sistem yang “lebih sederhana”.

2. Memberikan algoritma yang jelas untuk mencapainya.

3. Menjelaskan bagaimana membaca solusi dari bentuk tersebut.

### _Contoh operasi baris dan eliminasi_

$$
\begin{cases}
x_1 - x_2 + x_3 = 3 \\
2x_1 + x_2 + 8x_3 = 18 \\
4x_1 + 2x_2 - 3x_3 = -2
\end{cases}
$$

dari persamaan diatas kita menggunakan tiga operasi dasar garis

1. rescale_row(i,a) fungsi: mengalikan baris ke-i dengan skalar a
2. add_multiple_of_row(i, j, a) fungsi: menambahkan a x (baris ke-j) ke baris ke-i
3. swap_rows (i,j) fungsi: menukar baris ke-i dengan baris ke-j

python
A= matrix([[1, -1, 1, 3], [2, 1, 8, 18], [4, 2, -3, -2]])
#tambahkan -2 kali baris 0 ke baris 1
A.add_multiple_of_row(0,1,-2)
A.add_multiple_of_row(0, 2, -4)
A.add_multiple_of_row(1, 2, -2)
A.with_rescale_row(1, 1, 0/3)
A.with_rescale_row(2, 1, 0/-19)

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 3 & 6 & 12 \\
4 & 2 & -3 & -2
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 3 & 6 & 12 \\
0 & 6 & -7 & -14
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 3 & 6 & 12 \\
0 & 0 & -19 & -38
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 1 & 2 & 4 \\
0 & 0 & -19 & -38
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & -1 & 1 & 3 \\
0 & 1 & 2 & 4 \\
0 & 0 & 1 & 2
\end{bmatrix}
$$

hasil matrix diatas diubah kembali menjadi sistem persamaaan

<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <mtable displaystyle="true" columnalign="right" columnspacing="0em" rowspacing="3pt">
    <mtr>
      <mtd>
        <mtable displaystyle="true" columnalign="right center left" columnspacing="0em 0.278em" rowspacing="3pt">
          <mtr>
            <mtd>
              <msub>
                <mi>x</mi>
                <mn>1</mn>
              </msub>
              <mo>&#x2212;</mo>
              <msub>
                <mi>x</mi>
                <mn>2</mn>
              </msub>
              <mo>+</mo>
              <msub>
                <mi>x</mi>
                <mn>3</mn>
              </msub>
            </mtd>
            <mtd>
              <mi></mi>
              <mo>=</mo>
            </mtd>
            <mtd>
              <mn>3</mn>
            </mtd>
          </mtr>
          <mtr>
            <mtd>
              <msub>
                <mi>x</mi>
                <mn>2</mn>
              </msub>
              <mo>+</mo>
              <mn>2</mn>
              <msub>
                <mi>x</mi>
                <mn>3</mn>
              </msub>
            </mtd>
            <mtd>
              <mi></mi>
              <mo>=</mo>
            </mtd>
            <mtd>
              <mn>4</mn>
            </mtd>
          </mtr>
          <mtr>
            <mtd>
              <msub>
                <mi>x</mi>
                <mn>3</mn>
              </msub>
            </mtd>
            <mtd>
              <mi></mi>
              <mo>=</mo>
            </mtd>
            <mtd>
              <mn>2</mn>
            </mtd>
          </mtr>
        </mtable>
      </mtd>
    </mtr>
  </mtable>
</math>

dan dapat ditemukan bahwa:

$$
\begin{cases}
x_1 - x_2 + x_3 = 3 \\
x_2 + 2x_3 = 4 \\
x_3 = 2
\end{cases}
$$

dapat diketahui bahwa X3=2 kita subtitusikan ke persamaan kedua

$$
x_2 + 2(2) = 4
$$

$$
x_2 = 0
$$

lalu hasil X2 kita subtitusikan ke persamaan pertama

$$
\begin{aligned}
x_1 - 0 + 2 &= 3 \\
x_1 + 2 &= 3 \\
x_1 &= 3 - 2 \\
x_1 &= 1
\end{aligned}
$$

bentuk himpunan penyelesaiannya (1,0, 2)

### _contoh penyelesaian sistem persamaan empat variabel_

python
B=Matriks([[1, 1, 1, 1, 10], [2, 1, -1, 1, 5], [1, -1, 2, -1,1], [3, 2, 1, 1, 12]])

$$
\begin{cases}
x_1 + x_2 + x_3 + x_4 = 10 \\
2x_1 + x_2 - x_3 + x_4 = 5 \\
x_1 - x_2 + 2x_3 - x_4 = 1 \\
3x_1 + 2x_2 + x_3 + x_4 = 12
\end{cases}
$$

bentuk matrixnya:

$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 10 \\
2 & 1 & -1 & 1 & 5 \\
1 & -1 & 2 & -1 & 1 \\
3 & 2 & 1 & 1 & 12
\end{bmatrix}
$$

$$
R_2 \rightarrow R_2 - 2R_1
$$

$$
R_3 \rightarrow R_3 - R_1
$$

$$
R_4 \rightarrow R_4 - 3R_1
$$

$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 10 \\
0 & -1 & -3 & -1 & -15 \\
0 & -2 & 1 & -2 & -9 \\
0 & -1 & -2 & -2 & -18
\end{bmatrix}
$$

$$
R_3 \rightarrow R_3 - 2R_2
$$

$$
R_4 \rightarrow R_4 - R_2
$$

$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 10 \\
0 & -1 & -3 & -1 & -15 \\
0 & 0 & 7 & 0 & 21 \\
0 & 0 & 1 & -1 & -3
\end{bmatrix}
$$

$$
R_4 \rightarrow R_4 - \frac{1}{7}R_3
$$

$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 10 \\
0 & -1 & -3 & -1 & -15 \\
0 & 0 & 7 & 0 & 21 \\
0 & 0 & 0 & -1 & -6
\end{bmatrix}
$$

$$
R_2 \rightarrow -R_2
$$

$$
R_3 \rightarrow \frac{1}{7}R_3
$$

$$
R_4 \rightarrow -R_4
$$

$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 10 \\
0 & 1 & 3 & 1 & 15 \\
0 & 0 & 1 & 0 & 3 \\
0 & 0 & 0 & 1 & 6
\end{bmatrix}
$$

$$
\begin{cases}
x_1 + x_2 + x_3 + x_4 = 10 \\
x_2 + 3x_3 + x_4 = 15 \\
x_3 = 3 \\
x_4 = 6
\end{cases}
$$

$$
x_4 = 6
$$

$$
x_3 = 3
$$

subtitusikan ke persamaan kedua

$$
x_2 + 3(3) + 6 = 15
$$

$$
x_2 + 9 + 6 = 15
$$

$$
x_2 = 0
$$

subtitusikan ke persamaan pertama

$$
\begin{aligned}
x_1 + 0 + 3 + 6 &= 10 \\
x_1 + 9 &= 10 \\
x_1 &= 1
\end{aligned}
$$

himpunan penyelesaian:

$$
(x_1, x_2, x_3, x_4) = (1,0,3,6)
$$
