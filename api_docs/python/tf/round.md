<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.round" />
</div>

# tf.round

``` python
round(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Math > Basic Math Functions](../../../api_guides/python/math_ops.md#Basic_Math_Functions)

Rounds the values of a tensor to the nearest integer, element-wise.

Rounds half to even.  Also known as bankers rounding. If you want to round
according to the current system rounding mode use tf::cint.
For example:

```python
x = tf.constant([0.9, 2.5, 2.3, 1.5, -4.5])
tf.round(x)  # [ 1.0, 2.0, 2.0, 2.0, -4.0 ]
```

#### Args:

* <b>`x`</b>: A `Tensor` of type `float32` or `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of same shape and type as `x`.