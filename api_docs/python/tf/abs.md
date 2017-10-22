<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.abs" />
</div>

# tf.abs

``` python
abs(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Math > Basic Math Functions](../../../api_guides/python/math_ops.md#Basic_Math_Functions)

Computes the absolute value of a tensor.

Given a tensor `x` of complex numbers, this operation returns a tensor of type
`float32` or `float64` that is the absolute value of each element in `x`. All
elements in `x` must be complex numbers of the form \\(a + bj\\). The
absolute value is computed as \\( \sqrt{a^2 + b^2}\\).  For example:
```python
x = tf.constant([[-2.25 + 4.75j], [-3.25 + 5.75j]])
tf.abs(x)  # [5.25594902, 6.60492229]
```

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor` of type `float32`, `float64`, `int32`,
    `int64`, `complex64` or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` the same size and type as `x` with absolute
  values.
Note, for `complex64` or `complex128' input, the returned `Tensor` will be
  of type `float32` or `float64`, respectively.