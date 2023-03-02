# SVD

**SVD** 将任意矩阵 $A$ 分解为三个部分： $A = U \Sigma V^T$ 。其中， $U$ 和 $V$ 分别是 $A$ 中的 column space 和 row space 的 bases，并且它们：
* 长度为 1
* 互相 orthogonal

> $u_1, \\ \dots \\ , u_r \\ \text{is an orthonormal basis for the column space}$  
> $v_1, \\ \dots \\ , v_r \\ \text{is an othornormal basis for the row space}$

这样，我们的 $U$ 和 $V$ 分别是 $m\*r$ 和 $n\*r$ 的。不过我们可以更进一步，保持 $U$ 和 $V$ 的 orthogonal matrix 性质，填充向量使得它们变成一个方阵：

> $u_r+1, \\ \dots \\ , u_m \\ \text{is an orthonormal basis for the left null space}$  
> $v_r+1, \\ \dots \\ , v_n \\ \text{is an orthonormal basis for the null space}$
