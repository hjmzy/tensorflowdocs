<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.realdiv" />
</div>

# tf.realdiv

``` python
realdiv(
    x,
    y,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_math_ops.py`.

See the guide: [Math > Arithmetic Operators](../../../api_guides/python/math_ops.md#Arithmetic_Operators)

Returns x / y element-wise for real types.

If `x` and `y` are reals, this will return the floating-point division.

*NOTE*: `Div` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`, `uint8`, `int8`, `uint16`, `int16`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.