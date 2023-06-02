# 两个向量空间的交集（Learned From Introducing to Linear Algebra）

对于两个向量空间的 _basis_ 组成的矩阵 $V$ 和 $W$，我们可以通过把这两个向量空间的 _basis_ 组成的矩阵合并：

$$ M = \begin{bmatrix} V & W \end{bmatrix} $$

随后求出 $M$ 矩阵的 _row echelon form matrix_ $R$。我们可以从 $R$ 的 _nullspace_ 得到这两个向量的交集。 $N(R)$ 的 _dimension_ 即是交集的 _dimension_。

$N(R)$ 的 _special solution（同时也是 basis）_ 展现了 $V$ 和 $W$ 交集情况，以以下的 $V$ 和 $W$ 为例子：

$$
V = \begin{bmatrix}
1 & 2 \\
1 & 3 \\
1 & 2
\end{bmatrix}, W = \begin{bmatrix}
5 & 4 \\
6 & 3 \\
5 & 1
\end{bmatrix}
$$

可得：

$$
R = rref(\begin{bmatrix} V & W \end{bmatrix}) = \begin{bmatrix}
1 & 0 & 3 & 0 \\
0 & 1 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
$$

其中有 _special solution_： $\begin{bmatrix} -3 \\\ -1 \\\ 1 \\\ 0 \end{bmatrix}$ ，
换句话说， $W$ 的其中一个 basis 在 $V$ 的向量空间中（是 $V$ 的 basis 的一个 combination）：

$$
\begin{bmatrix} 
5 \\ 
6 \\ 
5 
\end{bmatrix} = 3 * \begin{bmatrix} 
1 \\ 
1 \\ 
1 \end{bmatrix} + 1 * \begin{bmatrix} 
2 \\ 
3 \\ 
2 
\end{bmatrix}
$$

那么，向量空间 $W$ 中的向量 $w$，满足：

$$
w = c * \begin{bmatrix} 
5 \\
6 \\
5
\end{bmatrix} + 0 * \begin{bmatrix} 
4 \\
3 \\
1
\end{bmatrix}
$$

都在向量空间 $V$ 中。
换句话说，这两个向量空间的交集的 _basis_ 是 $\begin{bmatrix} 5 \\\ 6 \\\ 5 \end{bmatrix}$，具有 _dimension = 1_，与 $N(R)$ 的 _dimension_ 相同。

## 总结

1. 两个向量空间 $V$ 和 $W$ 的交集可以从
$\begin{bmatrix} V & W \end{bmatrix}$ 
的 _row echelon form_ $R$ 获得

2. $R$ 的 _free variable_ 在原本的矩阵 
$\begin{bmatrix} V & W \end{bmatrix}$ 
所对应的 _column_ 就是交集的 _basis_

3. 由 _2_ 可知，两个向量空间的交集的 _dimension_ 与 $N(R)$ 的 _dimension_ 相同。
