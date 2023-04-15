# 线性变换的矩阵

线性变换的矩阵是对输入空间的基依次进行线性变换得到的矩阵：

$$
M = \begin{bmatrix} T(v_1) & T(v_2) & \dots \end{bmatrix}
$$

## 不同的基

考虑这样一个线性变换： $T (v) = v : V \rightarrow W$，其中，基 $V$ 和 基 $W$ 均张成了一个 $R^2$ 的向量空间。

> 我们用 **不规范** 的符号 $T : V \rightarrow W$ 来表示一个线性变换，其中 $V$ 和 $W$ 都是基组成的矩阵。
> 这些符号表示了一个线性变换 $T$，它的输入空间是基 $V$ 张成的向量空间，输出空间是 基 $W$ 张成的向量空间。

当 $V = W$ 时，线性变换的矩阵显然是单位矩阵 $I$。
然而，在 $V$ 与 $W$ 不同时，线性变换的矩阵 更明显地 表示了 输入空间的基向量 在 输出空间 中的 基向量的组合。

我们考虑一个具体的例子，假设：

$$
V = \begin{bmatrix}
3 & 6 \\
3 & 8
\end{bmatrix}
\quad
W = \begin{bmatrix}
3 & 0 \\
1 & 2
\end{bmatrix}
$$

我们尝试将基 $V$ 用基 $W$ 的线性组合（Linear Combination）表示：

$$
\begin{align}
v_1 = \mathbf{1} w_1 + \mathbf{1} w_2  \\
v_2 = \mathbf{2} w_1 + \mathbf{3} w_2
\end{align}
$$

不难发现加粗的系数显然可以组成一个矩阵 $B$：

$$
WB = V \quad \text{gives} \quad B = W^{-1} V
$$

> 只有在线性变换 $T$ 的 Range 为输出向量空间时，等式才成立。否则，对于那些处于 Kernel 中的基向量 $v$，其对应的线性组合是 $\mathbf{0}$
