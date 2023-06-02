# 复数乘法

两个复数相乘可以获得一个新的复数，这不禁让人想到将左边的复数变成一个矩阵，将复数相乘转变为矩阵和向量的应用。我们不妨先从基向量开始：
考虑基向量 $1$ 和 $i$，和任意复数 $v = a + bi$
$v$ 乘上 $1$ 都是它本身，因此左边的复数变成的矩阵应当形如：

$$
M_{\hat{i}} = \begin{bmatrix}
a & ? \\
b & ?
\end{bmatrix}
\begin{bmatrix}
1 \\
0
\end{bmatrix}
$$

类似的， $v$ 乘上 $i$ 会变成 $-b + ai$：

$$
M_{\hat{j}} = \begin{bmatrix}
? & -b \\
? & a
\end{bmatrix}
\begin{bmatrix}
0 \\
1
\end{bmatrix}
$$

考虑任意复数 $w = c + di$：

$$
\begin{align}
v \times w & = v \times c + v \times di \\
           & = M_{\hat{i}} \begin{bmatrix} c \\
               0 \end{bmatrix} + M_{\hat{j}} \begin{bmatrix} 0 \\
               d \end{bmatrix}
\end{align}
$$

我们发现，如果有矩阵 

$$
M = \begin{bmatrix} 
a & -b \\
b & a 
\end{bmatrix}
$$

来代替 $M_{\hat{i}}$ 和 $M_{\hat{j}}$，并不会影响计算结果，因此：

$$
\begin{align}
v \times w & = M \begin{bmatrix} c \\
               0 \end{bmatrix} + M \begin{bmatrix} 0 \\
               d \end{bmatrix} \\
           & = M ( \begin{bmatrix} c \\
               0 \end{bmatrix} + \begin{bmatrix} 0 \\
               d \end{bmatrix} ) \\
           & = M \begin{bmatrix} c \\
               d \end{bmatrix}
\end{align}
$$
