# 矩阵的 rank 与其 Column Space 和 Row Space 的关系

> 定义：rank 是矩阵中主元的个数，用 $r$ 表示。

## Row Space

关于行空间的关系相当平凡，我们可以在 _row echelon form matrix_ $R$ 中找到主元，只有主元所在的行是 nonzero 的。
并且，每个主元所在的行都是 _independent_ 的，同时 $R$ 的 _row space_ 与原先矩阵的 _row space_ 是相同的；
所以，这些主元所在的行就是 _row space_ 的 _basis_，而它们有 $r$ 个，因此 _row space_ 的 _dimension_ 是 $r$。

## Column Space

我们可以从矩阵的 _nullspace_ 中找到关于 _column space_ 的 _dimension_ 的信息。
_Nullspace_ 的 _special solutions（这里特指只有一个 free variable 为 1 的 solution）_ 揭示了矩阵 _column_ 的组合与独立关系，
同时也揭示了 _pivot column（或者是 basis）_ 的所在。

$$
\text{The dimension of the column space} = \text{pivot column} = n - \text{the number of free variable} = n - (n - r) = r
$$
