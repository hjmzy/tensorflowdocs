<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.cholesky" />
</div>

# tf.cholesky

### Aliases:

* `tf.cholesky`
* `tf.linalg.cholesky`

``` python
cholesky(
    input,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_linalg_ops.py`.

See the guide: [Math > Matrix Math Functions](../../../api_guides/python/math_ops.md#Matrix_Math_Functions)

Computes the Cholesky decomposition of one or more square matrices.

The input is a tensor of shape `[..., M, M]` whose inner-most 2 dimensions
form square matrices.

The input has to be symmetric and positive definite. Only the lower-triangular
part of the input will be used for this operation. The upper-triangular part
will not be read.

The output is a tensor of the same shape as the input
containing the Cholesky decompositions for all input submatrices `[..., :, :]`.

**Note**: The gradient computation on GPU is faster for large matrices but
not for large batch dimensions when the submatrices are small. In this
case it might be faster to use the CPU.

#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float64`, `float32`, `complex64`, `complex128`.
    Shape is `[..., M, M]`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`. Shape is `[..., M, M]`.