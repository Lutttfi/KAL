# _3. Penyelesaian (SPL) Tiga Variabel dan Empat Variabel Menggunakan Eliminasi Geussian_

_1. Soal nomer satu diberikan (SPL) tiga variabel dengan soal :_

$$
\begin{cases}
2x + y - z = 8 \\
-3x - y + 2z = -11 \\
-2x + y + 2z = -3
\end{cases}
$$

Tampilan Code nya untuk di tools sage :

```python
import numpy as np

M1 = matrix(QQ,[[2, 1, -1, 8], [-3, -1, 2, -11], [-2, 1, 2, -3]])
show(M1)
```

# 1. Buat pivot 1 di Baris 0 (R0 = 1/2 \* R0)

```python
import numpy as np
M1.rescale_row(0, 1/2) #
print ("")
show (M1)
```

# 2. Nolkan kolom 0 di bawah pivot

```python
import numpy as np
M1.add_multiple_of_row(1, 0, 3) # R1 = 3*R0 + R1
show (M1)
M1.add_multiple_of_row(2, 0, 2) # R2 = 2*R0 + R2
show (M1)
```

# 3. Buat pivot 1 di Baris 1 (R1 = 2 \* R1)

```python
import numpy as np
M1.rescale_row(1, 2) #
show (M1)
```

# 4. Nolkan kolom 1 di bawah pivot

```python
import numpy as np
M1.add_multiple_of_row(2, 1, -2) # R2 = -2\*R1 + R2
show (M1)
```

# 5. Buat pivot 1 di Baris 2 (R2 = -1 \* R2)

```python
import numpy as np
M1.rescale_row(2, -1) #

show(M1)
```

_Hasil Run Code 1_

![Hasil Soal 2](_static/RunCode.png)
_2. Soal nomer dua diberikan (SPL) empat variabel dengan soal :_

$$
\begin{cases}
w + x + y + z = 10 \\
2w + 3x + y - z = 7 \\
3w + 2x + 2y + z = 17 \\
4w + x - y + 2z = 10
\end{cases}
$$

Tampilan Code nya untuk di tools sage :

# Inisialisasi Matriks 4 Variabel (Gunakan QQ agar tidak error)

```python
import numpy as np
M2 = matrix(QQ, [
[1, 1, 1, 1, 10],
[2, 3, 1, -1, 7],
[3, 2, 2, 1, 17],
[4, 1, -1, 2, 10]
])

print("Matriks Awal:")
show(M2)
```

# 1. Nolkan kolom 0 di bawah pivot Baris 0

```python
import numpy as np
M2.add_multiple_of_row(1, 0, -2)
M2.add_multiple_of_row(2, 0, -3)
M2.add_multiple_of_row(3, 0, -4)
```

# 2. Nolkan kolom 1 di bawah pivot Baris 1

```python
import numpy as np
M2.add_multiple_of_row(2, 1, 1)
M2.add_multiple_of_row(3, 1, 3)
```

# 3. Buat pivot 1 di Baris 2 dan nolkan di bawahnya

```python
import numpy as np
M2.rescale_row(2, -1/2)
M2.add_multiple_of_row(3, 2, 8)
```

# 4. Buat pivot 1 di Baris 3

```python
import numpy as np
M2.rescale_row(3, -1/6)

print("Matriks Hasil Akhir (Eselon Baris):")
show(M2)
```

_Hasil Run Code 2_
![Hasil Soal 1](_static/RunCode2.png)
