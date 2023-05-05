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

## 换基

考虑一个线性变换 $T : I \rightarrow I$（其中 $I$ 都是 $R^2$ 的 `standard basis`），它将平面中的向量投影到直线 $y = -x$ 上，不难得出线性变换 $T$ 的矩阵是：

$$
\begin{align}
  Ai & = \begin{bmatrix} 
    \frac{1}{2} \\
    -\frac{1}{2} 
  \end{bmatrix} \\
  Aj & = \begin{bmatrix}
    -\frac{1}{2} \\
    \frac{1}{2}
  \end{bmatrix} \\
  A & = \begin{bmatrix}
    \frac{1}{2} & -\frac{1}{2} \\
    -\frac{1}{2} & \frac{1}{2}
  \end{bmatrix}
\end{align}
$$

但这个矩阵看起来非常的……分数，不过线性变换的矩阵本质上是 基向量进行线性变换 后 在输出向量空间中的 组合，如果我们选择 `eigenvector` 作为输入基和输出基，矩阵 $A_{new}$ 就会变成：

$$
\begin{align}
  x_1 & = \begin{bmatrix}
    1 \\
    -1
    \end{bmatrix} \quad \text{with eigenvalue} \quad 1 \\
  x_2 & = \begin{bmatrix}
    1 \\
    1
    \end{bmatrix} \quad \text{with eigenvalue} \quad 0 \\
  A & = \begin{bmatrix}
    1 & 0 \\
    0 & 0
    \end{bmatrix} \\
    & = \begin{bmatrix}
    \lambda_1 & 0 \\
    0 & \lambda_2
    \end{bmatrix} \\
    & = \Lambda
\end{align}
$$

同一个线性变换在不同基向量下的矩阵显然有所不同，但直觉上，这两者似乎有些联系，我们能不能找到 用 在 `standard basis` 下的矩阵 $A$ 和 其他的一些东西 来 表示 在新的基向量下的矩阵 $A_{new}$？
只看矩阵似乎看不出什么门道，我们不如先从线性变换上下手：

$$
\begin{align}
  T_{standard} & : I \rightarrow I \quad \text{with matrix} A \\
  T_{new}      & : X \rightarrow X \quad \text{with matrix} A_{new}
\end{align}
$$

似乎可以从中看出：

$$
\begin{align}
% DO FUCKING ALIGN FOR TEXT!!
  T_{in}(v) = v  & : X \rightarrow I \quad \text{with matrix} \quad B_{in} \\
  T              & : I \rightarrow I \quad \text{with matrix} \quad A      \\
  T_{out}(v) = v & : I \rightarrow X \quad \text{with matrix} \quad B_{out}
\end{align}
\text{then we have:} \quad T_{new} = T_{out} \cdot T \cdot T_{in} : X \rightarrow X \quad \text{with matrix} \quad B_{out} A B_{in}
$$

而显然 $B_{in} = X$ 和 $B_{out} = X^{-1}$
