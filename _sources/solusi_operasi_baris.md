# Penyelesaian SPL dengan Operasi Baris Elementer

## Operasi Baris Elementer (OBE)

Terdapat tiga jenis operasi baris elementer:

1. Menukar dua baris
2. Mengalikan baris dengan konstanta bukan nol
3. Menambahkan kelipatan baris lain ke suatu baris

---

## Contoh Sistem

$$
\begin{cases}
2x + y = 5 \\
x - y = 1
\end{cases}
$$

---

## Bentuk Matriks Augmented

$$
\left[
\begin{array}{cc|c}
2 & 1 & 5 \\
1 & -1 & 1
\end{array}
\right]
$$

---

## Langkah Eliminasi

### Langkah 1

$$
R_2 \rightarrow R_2 - \frac{1}{2}R_1
$$

$$
\left[
\begin{array}{cc|c}
2 & 1 & 5 \\
0 & -\frac{3}{2} & -\frac{3}{2}
\end{array}
\right]
$$

### Langkah 2

$$
R_2 \rightarrow R_2 - \frac{1}{2}R_1
$$

$$
\left[
\begin{array}{cc|c}
2 & 1 & 5 \\
0 & -\frac{3}{2} & -\frac{3}{2}
\end{array}
\right]
$$

---

## Substitusi Balik

Diperoleh:

$$
y = 1
$$

Substitusi ke persamaan pertama:

$$
2x + 1 = 5
$$

$$
x = 2
$$

---

## Hasil Akhir

$$
(x,y) = (2,1)
$$

---

# Implementasi Eliminasi Gauss dengan Python

```python
import numpy as np

def eliminasi_gauss(A):
    A = A.astype(float)
    n = len(A)

    for i in range(n):

        if A[i][i] == 0:
            for j in range(i+1, n):
                if A[j][i] != 0:
                    A[[i, j]] = A[[j, i]]
                    break

        pivot = A[i][i]
        A[i] = A[i] / pivot

        for j in range(i+1, n):
            faktor = A[j][i]
            A[j] = A[j] - faktor * A[i]

    return A


def gauss_solve(A):
    A = eliminasi_gauss(A)
    n = len(A)
    x = np.zeros(n)

    for i in range(n-1, -1, -1):
        x[i] = A[i][-1] - np.dot(A[i][i+1:n], x[i+1:n])

    return x


A = np.array([[2., 1., 5.],
              [1., -1., 1.]])

solusi = gauss_solve(A)

print("Solusi SPL:")
print("x =", solusi[0])
print("y =", solusi[1])
```
