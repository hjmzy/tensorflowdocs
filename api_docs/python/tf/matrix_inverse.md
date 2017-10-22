<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.matrix_inverse" />
</div>

# tf.matrix_inverse

### Aliases:

* `tf.linalg.inv`
* `tf.matrix_inverse`

``` python
matrix_inverse(
    input,
    adjoint=False,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_linalg_ops.py`.

See the guide: [Math > Matrix Math Functions](../../../api_guides/python/math_ops.md#Matrix_Math_Functions)

Computes the inverse of one or more square invertible matrices or their

adjoints (conjugate transposes).

The input is a tensor of shape `[..., M, M]` whose inner-most 2 dimensions
form square matrices. The output is a tensor of the same shape as the input
containing the inverse for all input submatrices `[..., :, :]`.

The op uses LU decomposition with partial pivoting to compute the inverses.

If a matrix is not invertible there is no guarantee what the op does. It
may detect the condition and raise an exception or it may simply return a
garbage result.

#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float64`, `float32`, `complex64`, `complex128`.
    Shape is `[..., M, M]`.
* <b>`adjoint`</b>: An optional `bool`. Defaults to `False`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`. Shape is `[..., M, M]`.



#### numpy compatibility
  Equivalent to np.linalg.inv

