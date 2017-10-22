<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.bitwise.left_shift" />
</div>

# tf.bitwise.left_shift

``` python
left_shift(
    x,
    y,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_bitwise_ops.py`.

Elementwise computes the bitwise left-shift of `x` and `y`.

If `y` is negative, or greater than or equal to the width of `x` in bits the
result is implementation defined.

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `int8`, `int16`, `int32`, `int64`, `uint8`, `uint16`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.