# 矩阵乘法的基础规则证明

## 分配律

考虑矩阵 $A$ 和两个向量 $i$ $j$，并且 $Ai$ 和 $Aj$ 是合法的。
用 $a_n$ 来表示 $A$ 的第 $n$ 个 _column_。

$$
\begin{equation}
\begin{split}
A (i + j)
& = a_1 * (i + j)_1 + a_2 * (i + j)_2 + \dots \\ 
& = a_1 * i_1 + a_1 * j_1 + a_2 * i_2 + a_2 * j_2 + \dots \\
& = a_1 * i_1 + a_2 * i_2 + \dots + a_1 * j_1 + a_2 * j_2 \dots \\
& = Ai + Aj
\end{split}
\end{equation}
$$

> 第二步使用了向量标量乘的分配律。

我们可以由此证明 $A (B + C) = AB + AC$，同样的，使用 $b_n$ 和 $c_n$ 来表示 $B$ 和 $C$ 的第 $n$ 个 _column_：

$$
\begin{equation}
\begin{split}
A (B + C)
& = \begin{bmatrix} A (b_1 + c_1) & A (b_2 + c_2) & \dots \end{bmatrix} \\
& = \begin{bmatrix} A b_1 + A c_1 & A b_2 + A c_2 & \dots \end{bmatrix} \\
& = \begin{bmatrix} A b_1 & A b_2 & \dots \end{bmatrix} + \begin{bmatrix} A c_1 & A c_2 & \dots \end{bmatrix} \\
& = AB + AC
\end{split}
\end{equation}
$$

对于向左分配也是类似的：
考虑矩阵 $A$ $B$ 和向量 $c$，并且 $Ac$、$Bc$ 和 $A + B$ 合法

$$
\begin{equation}
\begin{split}
(A + B) c
& = \begin{bmatrix} c_1 * (a_1 + b_1) & c_2 * (a_2 + b_2) & \dots \end{bmatrix} \\
& = \begin{bmatrix} c_1 * a_1 + c_1 * b_1 & c_2 * a_2 + c_2 * b_2 & \dots \end{bmatrix} \\
& = \begin{bmatrix} c_1 * a_1 & c_2 * a_2 & \dots \end{bmatrix} + \begin{bmatrix} c_1 * b_1 & c_2 * b_2 & \dots \end{bmatrix} \\
& = Ac + Bc
\end{split}
\end{equation}
$$

$$
\begin{equation}
\begin{split}
(A + B) C
& = \begin{bmatrix} (A + B) c_1 & (A + B) c_2 & \dots \end{bmatrix} \\
& = \begin{bmatrix} Ac_1 + Bc_1 & Ac_2 + Bc_2 & \dots \end{bmatrix} \\
& = \begin{bmatrix} Ac_1 & Ac_2 & \dots \end{bmatrix} + \begin{bmatrix} Bc_1 & Bc_2 & \dots \end{bmatrix} \\
& = AC + BC
\end{split}
\end{equation}
$$

## 标量乘结合律

考虑矩阵 $A$、向量 $b$ 和一个标量 $c$，并且 $Ab$ 是合法的。

$$
\begin{equation}
\begin{split}
Acb
& = cb_1 * a_1 + cb_2 * a_2 + \dots \\
& = c (b_1 * a_1 + b_2 * a_2 + \dots) \\
& = cAb
\end{split}
\end{equation}
$$

进而得到：

$$
\begin{equation}
\begin{split}
AcB
& = \begin{bmatrix} Acb_1 & Acb_2 & \dots \end{bmatrix} \\
& = \begin{bmatrix} cAb_1 & cAb_2 & \dots \end{bmatrix} \\
& = c \begin{bmatrix} Ab_1 & Ab_2 & \dots \end{bmatrix} \\
& = cAB
\end{split}
\end{equation}
$$

## 结合律

考虑矩阵 $A$ $B$ 和一个向量 $c$，并且 $ABc$ 是合法的。

$$
\begin{equation}
\begin{split}
(AB)c
& = \begin{bmatrix} Ab_1 & Ab_2 & \dots \end{bmatrix} c \\
& = c_1 * Ab_1 + c_2 * Ab_2 + \dots \\
& = A (c_1 * b_1) + A (c_2 * b_2) + \dots \\
& = A (c_1 * b_1 + c_2 * b_2 + \dots) \\
& = A(Bc)
\end{split}
\end{equation}
$$

之后我们就可以对三个矩阵的乘法的结合律进行证明了：

$$
\begin{equation}
\begin{split}
(AB)C
& = \begin{bmatrix} (AB)c_1 & (AB)c_2 & \dots \end{bmatrix} \\
& = \begin{bmatrix} A(Bc_1) & A(Bc_2) & \dots \end{bmatrix} \\
& = A \begin{bmatrix} Bc_1 & Bc_2 & \dots \end{bmatrix} \\
& = A(BC)
\end{split}
\end{equation}
$$

> 事实上关于 $ABc$ 有一个非常优雅的证明：  
> 把矩阵之间的乘法（ $AB$ ）看作是函数复合，而矩阵和向量之间的乘法看作是函数应用，那么：  
> $A(Bc)$ 实际上就是： $A(B(c))$，而 $(AB)c$ 是 `(\x. A(B(x))) c`，规约之后就是 $A(B(c))$。  
> 但我个人觉得这个证明有点稍微意识流，有种本能在抗拒这个证明。  
> 但这个证明的美妙是客观的。
