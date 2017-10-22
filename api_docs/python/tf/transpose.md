<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.transpose" />
</div>

# tf.transpose

``` python
transpose(
    a,
    perm=None,
    name='transpose',
    conjugate=False
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/array_ops.py).

See the guides: [Math > Matrix Math Functions](../../../api_guides/python/math_ops.md#Matrix_Math_Functions), [Tensor Transformations > Slicing and Joining](../../../api_guides/python/array_ops.md#Slicing_and_Joining)

Transposes `a`. Permutes the dimensions according to `perm`.

The returned tensor's dimension i will correspond to the input dimension
`perm[i]`. If `perm` is not given, it is set to (n-1...0), where n is
the rank of the input tensor. Hence by default, this operation performs a
regular matrix transpose on 2-D input Tensors. If conjugate is True and
`a.dtype` is either `complex64` or `complex128` then the values of `a`
are conjugated and transposed.

For example:

```python
x = tf.constant([[1, 2, 3], [4, 5, 6]])
tf.transpose(x)  # [[1, 4]
                 #  [2, 5]
                 #  [3, 6]]

# Equivalently
tf.transpose(x, perm=[1, 0])  # [[1, 4]
                              #  [2, 5]
                              #  [3, 6]]

# If x is complex, setting conjugate=True gives the conjugate transpose
x = tf.constant([[1 + 1j, 2 + 2j, 3 + 3j],
                 [4 + 4j, 5 + 5j, 6 + 6j]])
tf.transpose(x, conjugate=True)  # [[1 - 1j, 4 - 4j],
                                 #  [2 - 2j, 5 - 5j],
                                 #  [3 - 3j, 6 - 6j]]

# 'perm' is more useful for n-dimensional tensors, for n > 2
x = tf.constant([[[ 1,  2,  3],
                  [ 4,  5,  6]],
                 [[ 7,  8,  9],
                  [10, 11, 12]]])

# Take the transpose of the matrices in dimension-0
# (this common operation has a shorthand `matrix_transpose`)
tf.transpose(x, perm=[0, 2, 1])  # [[[1,  4],
                                 #   [2,  5],
                                 #   [3,  6]],
                                 #  [[7, 10],
                                 #   [8, 11],
                                 #   [9, 12]]]
```

#### Args:

* <b>`a`</b>: A `Tensor`.
* <b>`perm`</b>: A permutation of the dimensions of `a`.
* <b>`name`</b>: A name for the operation (optional).
* <b>`conjugate`</b>: Optional bool. Setting it to `True` is mathematically equivalent
    to tf.conj(tf.transpose(input)).


#### Returns:

A transposed `Tensor`.