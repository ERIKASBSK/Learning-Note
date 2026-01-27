### 1) Addition / 加算（足し算）

```python
a = [1, 2]
print(a + a)
```

Result

```text
[1, 2, 1, 2]
```

```python
import numpy as np
a = np.array([1, 2])
print(a + a)
```

Result

```text
[2 4]
```

---

### 2) Multiplication / 乗算（かけ算）

```python
a = [1, 2]
print(a * 3)
```

Result

```text
[1, 2, 1, 2, 1, 2]
```

```python
import numpy as np
a = np.array([1, 2])
print(a * 3)
```

Result

```text
[3 6]
```

---

### 3) Matrix add (element-wise) / 行列の加算（要素ごと）

```python
A = [[1, 2], [3, 4]]
B = [[10, 20], [30, 40]]

C = [[A[i][j] + B[i][j] for j in range(2)] for i in range(2)]
print(C)
```

Result

```text
[[11, 22], [33, 44]]
```

```python
import numpy as np
A = np.array([[1, 2], [3, 4]])
B = np.array([[10, 20], [30, 40]])

print(A + B)
```

Result

```text
[[11 22]
 [33 44]]
```

---

### 4) Transpose / 転置

```python
A = [[1, 2], [3, 4]]

AT = [[A[j][i] for j in range(2)] for i in range(2)]
print(AT)
```

Result

```text
[[1, 3], [2, 4]]
```

```python
import numpy as np
A = np.array([[1, 2], [3, 4]])
print(A.T)
```

Result

```text
[[1 3]
 [2 4]]
```

---

### 5) Dot product / 内積

```python
v1 = [1, 2, 3]
v2 = [4, 5, 6]

dot = sum(x*y for x, y in zip(v1, v2))
print(dot)
```

Result

```text
32
```

```python
import numpy as np
v1 = np.array([1, 2, 3])
v2 = np.array([4, 5, 6])

print(v1 @ v2)
```

Result

```text
32
```
