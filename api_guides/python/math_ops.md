<!-- DO NOT EDIT! Automatically generated file. -->
# Math

Note: Functions taking `Tensor` arguments can also take anything accepted by
[`tf.convert_to_tensor`](../../api_docs/python/tf/convert_to_tensor.md).

[TOC]

Note: Elementwise binary operations in TensorFlow follow [numpy-style
broadcasting](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html).

<h2 id="Arithmetic_Operators">Arithmetic Operators</h2>

TensorFlow provides several operations that you can use to add basic arithmetic
operators to your graph.

*   [`tf.add`](../../api_docs/python/tf/add.md)
*   [`tf.subtract`](../../api_docs/python/tf/subtract.md)
*   [`tf.multiply`](../../api_docs/python/tf/multiply.md)
*   [`tf.scalar_mul`](../../api_docs/python/tf/scalar_mul.md)
*   [`tf.div`](../../api_docs/python/tf/div.md)
*   [`tf.divide`](../../api_docs/python/tf/divide.md)
*   [`tf.truediv`](../../api_docs/python/tf/truediv.md)
*   [`tf.floordiv`](../../api_docs/python/tf/floordiv.md)
*   [`tf.realdiv`](../../api_docs/python/tf/realdiv.md)
*   [`tf.truncatediv`](../../api_docs/python/tf/truncatediv.md)
*   [`tf.floor_div`](../../api_docs/python/tf/floor_div.md)
*   [`tf.truncatemod`](../../api_docs/python/tf/truncatemod.md)
*   [`tf.floormod`](../../api_docs/python/tf/floormod.md)
*   [`tf.mod`](../../api_docs/python/tf/floormod.md)
*   [`tf.cross`](../../api_docs/python/tf/cross.md)

<h2 id="Basic_Math_Functions">Basic Math Functions</h2>

TensorFlow provides several operations that you can use to add basic
mathematical functions to your graph.

*   [`tf.add_n`](../../api_docs/python/tf/add_n.md)
*   [`tf.abs`](../../api_docs/python/tf/abs.md)
*   [`tf.negative`](../../api_docs/python/tf/negative.md)
*   [`tf.sign`](../../api_docs/python/tf/sign.md)
*   [`tf.reciprocal`](../../api_docs/python/tf/reciprocal.md)
*   [`tf.square`](../../api_docs/python/tf/square.md)
*   [`tf.round`](../../api_docs/python/tf/round.md)
*   [`tf.sqrt`](../../api_docs/python/tf/sqrt.md)
*   [`tf.rsqrt`](../../api_docs/python/tf/rsqrt.md)
*   [`tf.pow`](../../api_docs/python/tf/pow.md)
*   [`tf.exp`](../../api_docs/python/tf/exp.md)
*   [`tf.expm1`](../../api_docs/python/tf/expm1.md)
*   [`tf.log`](../../api_docs/python/tf/log.md)
*   [`tf.log1p`](../../api_docs/python/tf/log1p.md)
*   [`tf.ceil`](../../api_docs/python/tf/ceil.md)
*   [`tf.floor`](../../api_docs/python/tf/floor.md)
*   [`tf.maximum`](../../api_docs/python/tf/maximum.md)
*   [`tf.minimum`](../../api_docs/python/tf/minimum.md)
*   [`tf.cos`](../../api_docs/python/tf/cos.md)
*   [`tf.sin`](../../api_docs/python/tf/sin.md)
*   [`tf.lbeta`](../../api_docs/python/tf/lbeta.md)
*   [`tf.tan`](../../api_docs/python/tf/tan.md)
*   [`tf.acos`](../../api_docs/python/tf/acos.md)
*   [`tf.asin`](../../api_docs/python/tf/asin.md)
*   [`tf.atan`](../../api_docs/python/tf/atan.md)
*   [`tf.cosh`](../../api_docs/python/tf/cosh.md)
*   [`tf.sinh`](../../api_docs/python/tf/sinh.md)
*   [`tf.asinh`](../../api_docs/python/tf/asinh.md)
*   [`tf.acosh`](../../api_docs/python/tf/acosh.md)
*   [`tf.atanh`](../../api_docs/python/tf/atanh.md)
*   [`tf.lgamma`](../../api_docs/python/tf/lgamma.md)
*   [`tf.digamma`](../../api_docs/python/tf/digamma.md)
*   [`tf.erf`](../../api_docs/python/tf/erf.md)
*   [`tf.erfc`](../../api_docs/python/tf/erfc.md)
*   [`tf.squared_difference`](../../api_docs/python/tf/squared_difference.md)
*   [`tf.igamma`](../../api_docs/python/tf/igamma.md)
*   [`tf.igammac`](../../api_docs/python/tf/igammac.md)
*   [`tf.zeta`](../../api_docs/python/tf/zeta.md)
*   [`tf.polygamma`](../../api_docs/python/tf/polygamma.md)
*   [`tf.betainc`](../../api_docs/python/tf/betainc.md)
*   [`tf.rint`](../../api_docs/python/tf/rint.md)

<h2 id="Matrix_Math_Functions">Matrix Math Functions</h2>

TensorFlow provides several operations that you can use to add linear algebra
functions on matrices to your graph.

*   [`tf.diag`](../../api_docs/python/tf/diag.md)
*   [`tf.diag_part`](../../api_docs/python/tf/diag_part.md)
*   [`tf.trace`](../../api_docs/python/tf/trace.md)
*   [`tf.transpose`](../../api_docs/python/tf/transpose.md)
*   [`tf.eye`](../../api_docs/python/tf/eye.md)
*   [`tf.matrix_diag`](../../api_docs/python/tf/matrix_diag.md)
*   [`tf.matrix_diag_part`](../../api_docs/python/tf/matrix_diag_part.md)
*   [`tf.matrix_band_part`](../../api_docs/python/tf/matrix_band_part.md)
*   [`tf.matrix_set_diag`](../../api_docs/python/tf/matrix_set_diag.md)
*   [`tf.matrix_transpose`](../../api_docs/python/tf/matrix_transpose.md)
*   [`tf.matmul`](../../api_docs/python/tf/matmul.md)
*   [`tf.norm`](../../api_docs/python/tf/norm.md)
*   [`tf.matrix_determinant`](../../api_docs/python/tf/matrix_determinant.md)
*   [`tf.matrix_inverse`](../../api_docs/python/tf/matrix_inverse.md)
*   [`tf.cholesky`](../../api_docs/python/tf/cholesky.md)
*   [`tf.cholesky_solve`](../../api_docs/python/tf/cholesky_solve.md)
*   [`tf.matrix_solve`](../../api_docs/python/tf/matrix_solve.md)
*   [`tf.matrix_triangular_solve`](../../api_docs/python/tf/matrix_triangular_solve.md)
*   [`tf.matrix_solve_ls`](../../api_docs/python/tf/matrix_solve_ls.md)
*   [`tf.qr`](../../api_docs/python/tf/qr.md)
*   [`tf.self_adjoint_eig`](../../api_docs/python/tf/self_adjoint_eig.md)
*   [`tf.self_adjoint_eigvals`](../../api_docs/python/tf/self_adjoint_eigvals.md)
*   [`tf.svd`](../../api_docs/python/tf/svd.md)


<h2 id="Tensor_Math_Function">Tensor Math Function</h2>

TensorFlow provides operations that you can use to add tensor functions to your
graph.

*   [`tf.tensordot`](../../api_docs/python/tf/tensordot.md)


<h2 id="Complex_Number_Functions">Complex Number Functions</h2>

TensorFlow provides several operations that you can use to add complex number
functions to your graph.

*   [`tf.complex`](../../api_docs/python/tf/complex.md)
*   [`tf.conj`](../../api_docs/python/tf/conj.md)
*   [`tf.imag`](../../api_docs/python/tf/imag.md)
*   [`tf.angle`](../../api_docs/python/tf/angle.md)
*   [`tf.real`](../../api_docs/python/tf/real.md)


<h2 id="Reduction">Reduction</h2>

TensorFlow provides several operations that you can use to perform
common math computations that reduce various dimensions of a tensor.

*   [`tf.reduce_sum`](../../api_docs/python/tf/reduce_sum.md)
*   [`tf.reduce_prod`](../../api_docs/python/tf/reduce_prod.md)
*   [`tf.reduce_min`](../../api_docs/python/tf/reduce_min.md)
*   [`tf.reduce_max`](../../api_docs/python/tf/reduce_max.md)
*   [`tf.reduce_mean`](../../api_docs/python/tf/reduce_mean.md)
*   [`tf.reduce_all`](../../api_docs/python/tf/reduce_all.md)
*   [`tf.reduce_any`](../../api_docs/python/tf/reduce_any.md)
*   [`tf.reduce_logsumexp`](../../api_docs/python/tf/reduce_logsumexp.md)
*   [`tf.count_nonzero`](../../api_docs/python/tf/count_nonzero.md)
*   [`tf.accumulate_n`](../../api_docs/python/tf/accumulate_n.md)
*   [`tf.einsum`](../../api_docs/python/tf/einsum.md)

<h2 id="Scan">Scan</h2>

TensorFlow provides several operations that you can use to perform scans
(running totals) across one axis of a tensor.

*   [`tf.cumsum`](../../api_docs/python/tf/cumsum.md)
*   [`tf.cumprod`](../../api_docs/python/tf/cumprod.md)

<h2 id="Segmentation">Segmentation</h2>

TensorFlow provides several operations that you can use to perform common
math computations on tensor segments.
Here a segmentation is a partitioning of a tensor along
the first dimension, i.e. it  defines a mapping from the first dimension onto
`segment_ids`. The `segment_ids` tensor should be the size of
the first dimension, `d0`, with consecutive IDs in the range `0` to `k`,
where `k<d0`.
In particular, a segmentation of a matrix tensor is a mapping of rows to
segments.

For example:

```python
c = tf.constant([[1,2,3,4], [-1,-2,-3,-4], [5,6,7,8]])
tf.segment_sum(c, tf.constant([0, 0, 1]))
  ==>  [[0 0 0 0]
        [5 6 7 8]]
```

*   [`tf.segment_sum`](../../api_docs/python/tf/segment_sum.md)
*   [`tf.segment_prod`](../../api_docs/python/tf/segment_prod.md)
*   [`tf.segment_min`](../../api_docs/python/tf/segment_min.md)
*   [`tf.segment_max`](../../api_docs/python/tf/segment_max.md)
*   [`tf.segment_mean`](../../api_docs/python/tf/segment_mean.md)
*   [`tf.unsorted_segment_sum`](../../api_docs/python/tf/unsorted_segment_sum.md)
*   [`tf.sparse_segment_sum`](../../api_docs/python/tf/sparse_segment_sum.md)
*   [`tf.sparse_segment_mean`](../../api_docs/python/tf/sparse_segment_mean.md)
*   [`tf.sparse_segment_sqrt_n`](../../api_docs/python/tf/sparse_segment_sqrt_n.md)


<h2 id="Sequence_Comparison_and_Indexing">Sequence Comparison and Indexing</h2>

TensorFlow provides several operations that you can use to add sequence
comparison and index extraction to your graph. You can use these operations to
determine sequence differences and determine the indexes of specific values in
a tensor.

*   [`tf.argmin`](../../api_docs/python/tf/argmin.md)
*   [`tf.argmax`](../../api_docs/python/tf/argmax.md)
*   [`tf.setdiff1d`](../../api_docs/python/tf/setdiff1d.md)
*   [`tf.where`](../../api_docs/python/tf/where.md)
*   [`tf.unique`](../../api_docs/python/tf/unique.md)
*   [`tf.edit_distance`](../../api_docs/python/tf/edit_distance.md)
*   [`tf.invert_permutation`](../../api_docs/python/tf/invert_permutation.md)
