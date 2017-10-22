<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.atan2" />
</div>

# tf.atan2

``` python
atan2(
    y,
    x,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_math_ops.py`.

Computes arctangent of `y/x` element-wise, respecting signs of the arguments.

This is the angle \( \theta \in [-\pi, \pi] \) such that
\[ x = r \cos(\theta) \]
and
\[ y = r \sin(\theta) \]
where \(r = \sqrt(x^2 + y^2) \).

#### Args:

* <b>`y`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
* <b>`x`</b>: A `Tensor`. Must have the same type as `y`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `y`.