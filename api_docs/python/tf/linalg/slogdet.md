<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.slogdet" />
</div>

# tf.linalg.slogdet

``` python
slogdet(
    input,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_linalg_ops.py`.

Computes the sign and the log of the absolute value of the determinant of

one or more square matrices.

The input is a tensor of shape `[N, M, M]` whose inner-most 2 dimensions
form square matrices. The outputs are two tensors containing the signs and
absolute values of the log determinants for all N input submatrices
`[..., :, :]` such that the determinant = sign*exp(log_abs_determinant).
The log_abs_determinant is computed as det(P)*sum(log(diag(LU))) where LU
is the LU decomposition of the input and P is the corresponding
permutation matrix.

#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `complex64`, `complex128`.
    Shape is `[N, M, M]`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A tuple of `Tensor` objects (sign, log_abs_determinant).

* <b>`sign`</b>: A `Tensor`. Has the same type as `input`. The signs of the log determinants of the inputs. Shape is `[N]`.
* <b>`log_abs_determinant`</b>: A `Tensor`. Has the same type as `input`. The logs of the absolute values of the determinants
    of the N input matrices.  Shape is `[N]`.