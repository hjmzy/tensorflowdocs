<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sqrt" />
</div>

# tf.sqrt

``` python
sqrt(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Math > Basic Math Functions](../../../api_guides/python/math_ops.md#Basic_Math_Functions)

Computes square root of x element-wise.

I.e., \\(y = \sqrt{x} = x^{1/2}\\).

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`. Must be one of the following types: `half`,
    `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor`, respectively. Has the same type as `x`.