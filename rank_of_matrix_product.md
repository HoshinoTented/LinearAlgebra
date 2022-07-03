# 矩阵乘法结果的 rank 与参与乘法的矩阵的 rank 的关系

考虑两个矩阵 $A$ 和 $B$，其中 $A$ 具有形状 $m * n$，$B$ 具有形状 $n * m$，因此 $AB$ 具有形状 $m * m$；  
设 $r_A$ 为 $A$ 的 _rank_，同样的，$r_B$ 为 $B$ 的 _rank_。

## rank(AB) 与 rank(B)

把 $AB$ 考虑为 $A$ 的 _column_ 的 _combinations_，
那么对于某个在 $B$ 中，不是 _pivot column_ 的 _column vector_ $b$，$b$ 一定是 _pivot column_ 的 _combination_，那么 $Ab$ 也一定是 $A$ 与 _pivot columns_ 的积的 _combination_：

$$
b = c_1 b_1 + c_2 b_2 + \dots + c_n b_n
$$

推导出：

$$
Ab = A (c_1 b_1 + c_2 b_2 + \dots + c_n b_n) = A (c_1 b_1) + A (c_2 b_2) + \dots + A (c_n b_n)
$$

因此，$rank(AB) \le rank(B)$

## rank(AB) 与 rank(A)

与 rank(B) 的操作类似，不过我们这次将 $AB$ 考虑为 $B$ 的 _row_ 的 _combination_：
对于某个在 $A$ 中，没有 _pivot_ 的 _row_ $a$，$a$ 一定是 _pivot row_ 的 _combination_，那么 $aB$ 也一定是 _pivot rows_ 与 $B$ 的积的 _combination_：

$$
a = c_1 a_1 + c_2 a_2 + \dots + c_n a_n
$$

推导出

$$
aB = (c_1 a_1 + c_2 a_2 + \dots + c_n a_n) B = (c_1 a_1) B + (c_2 a_2) B + \dots + (c_n a_n) B
$$

因此，$rank(AB) \le rank(A)$

> 另一个美妙的证明：$rank(B^T A^T) <= rank(A^T)$，由于 _transpose_ 不会改变矩阵的 _rank_，因此 $rank(AB) <= rank(A)$
