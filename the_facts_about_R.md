# 关于 _row echelon form matrix_ $R$ 的几个事实

## 制备 _Row Echelon Form Matrix_ $R$

对于任意矩阵 $M$，通过消元矩阵 $E$ 我们可以得到：$EM = U \ \text{or} \ M = LU$。
之后可以使用另一个消除主元上元素的矩阵 $U'$ 和将主元变化为 _1_ 的矩阵 $D$ 将 $U$ 变化为 $R$。考虑以下矩阵 $M$：

$$
M = \begin{bmatrix}
1 & 2 & 2 & 4 \\
3 & 8 & 6 & 16
\end{bmatrix} = \begin{bmatrix}
1 & 0 \\
3 & 1
\end{bmatrix} \begin{bmatrix}
1 & 0 \\
0 & 2
\end{bmatrix} \begin{bmatrix}
1 & 2 & 2 & 4 \\
0 & 1 & 0 & 2
\end{bmatrix} = L D U
$$

我们将 $U$ 中主元上方的元素使用类似的 _row operation_ 消除掉，得到 $R$：

$$
U = \begin{bmatrix}
1 & 2 & 2 & 4 \\
0 & 1 & 0 & 2
\end{bmatrix} = \begin{bmatrix}
1 & 2 \\
0 & 1
\end{bmatrix} \begin{bmatrix}
\mathbf{1} & \mathbf{0} & 2 & 0 \\
\mathbf{0} & \mathbf{1} & 0 & 2
\end{bmatrix} = U' R
$$

## $R$ 的 _row space_ 保持不变

无论是从 $M$ 到 $U$ 还是从 $U$ 到 $R$，使用的矩阵都是 _row operation_，或者说，矩阵乘法结果的每个 _row_ 都是先前矩阵的 _row_ 的 _combination_。
而这显然不会超越原先的 _row space_

## R 中的 pivot 和 free variable。

**Pivot**，或者叫主元，是 $R$ 中每一行第一个非 0 的元素，并且在当前对 $R$ 的定义中，这个元素一定是 $1$。
这样我们有个很美妙的性质：主元所在的 _column_ 可以重新排列，构成一个单位矩阵（对于刚才 $M$ 的 $R$ 不需要重新排列，单位矩阵被用粗体表示）

## 矩阵的 rank

> 定义：矩阵的 rank 是主元的个数，用 $r$ 表示。

对于刚才的矩阵 $M$，有两个主元，因此它的 _rank_ 是 2。

$$
r = 2
$$

## Free Variable

对于任意的矩阵 $A$，在 $Ax$ 中，没有 _pivot_ 的 _column_ 被称作 _free column_，而 _free column_ 所对应的 $x$ 的 _component_ 被称作 _free variable_。

## Nullspace

对于任意的矩阵 $A$，_nullspace_ 是所有使得 $Ax=0$ 成立的 $x$ 组成的向量空间，用 $N(A)$ 表示。
消元并不会改变 _nullspace_。对于任意 $x \in N(A)$：

$$
\begin{equation}
\begin{split}
Ax & = 0 \\
(LDU)x & = 0 \\
LD(Ux) & = 0 \\
D^{-1} L^{-1} LD (Ux) & = D^{-1} L^{-1} 0 \\
Ux & = 0
\end{split}
\end{equation}
$$

可得 $N(A) = N(U)$，同理可得 $N(U) = N(R)$。

$$
N(A) = N(U) = N(R)
$$

## Special Solution

对于任意的矩阵 $A$，_special solution_ 是一个非零的，使得 $Ax=0$ 成立的 $x$（显然它在 _nullspace_ 中）。
有一个非常简单但重要的找到 _special solution_ 的方法：把其中一个 _free variable_ 设置为 $1$，其他的 _free variable_ 设置为 $0$，然后通过简单的加减法填入剩下的空位，使得 $Ax=0$ 成立。以 $R$ 为例（$N(M) = N(R)$）：

$$
\begin{bmatrix}
\mathbf{1} & \mathbf{0} & 2 & 0 \\
\mathbf{0} & \mathbf{1} & 0 & 2
\end{bmatrix} \begin{bmatrix} 
x_1 \\\ x_2 \\\ 1 \\\ 0
\end{bmatrix}
$$

考虑第一行，主元是 $1$，第一个 _free variable_（也就是第三个 _component_）设置是 $1$，为了使得 $x_1 + 0 * x_2 + 2 * 1 + 0 * 0 = 0$ 成立，可得 $x_1 = -2$，这其实就是 _free column_ 的第一个元素的反！

同样我们可以求得 $x_2 = 0$，因此第一个 _special solution_ 是 $x_1 = \begin{bmatrix} -2 \\\ 0 \\\ 1 \\\ 0 \end{bmatrix}$。

$$
\begin{bmatrix}
\mathbf{1} & \mathbf{0} & 2 & 0 \\
\mathbf{0} & \mathbf{1} & 0 & 2
\end{bmatrix} \begin{bmatrix}
-2 \\
 0 \\
 1 \\
 0 
\end{bmatrix} = \mathbf{0}
$$

同理可得第二个 _special solution_ $x_2$：

$$
\begin{bmatrix}
\mathbf{1} & \mathbf{0} & 2 & 0 \\
\mathbf{0} & \mathbf{1} & 0 & 2
\end{bmatrix} \begin{bmatrix}
 0 \\
-2 \\
 0 \\
 1 
\end{bmatrix} = \mathbf{0}
$$

为什么这些 _special solution_ 是 _independent_？
这很显然，因为它们的 _free variable_ 部分形成了一个单位矩阵：

$$
\begin{bmatrix}
-2 &  0 \\
 0 & -2 \\
 \mathbf{1} & \mathbf{0} \\
 \mathbf{0} & \mathbf{1}
\end{bmatrix}
$$

为什么不会有更多的 _independent special solution_？假设存在非 0 的 $x$，使得 $Ax=0$，我们可以用 _special solution_ 将 $x$ 在 _free variable_ 上的元素消为 0：

$$
A(c_1x_1 + c_2x_2 + x') = 0
$$

此时 $x'$ 的所有 _free variable_ 都为 $0$，那么在非 _free variable_ 上的元素也一定为 $0$，否则这意味着有至少一个 _pivot column_ 是其他 _pivot column_ 的 _combination_，或者说它们是 _dependent_ 的，而这不可能。所以 $x$ 是 _independent special solution_ 的一个 _combination_，它落在 _nullspace_ 中。由于它是原先的 _independent special solution_ 的 _combination_，因此将它加入 _independent special solutions_ 中会破坏 _independent_。
