<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.logical_and" />
</div>

# tf.logical_and

``` python
logical_and(
    x,
    y,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_math_ops.py`.

See the guide: [Control Flow > Logical Operators](../../../api_guides/python/control_flow_ops.md#Logical_Operators)

Returns the truth value of x AND y element-wise.

*NOTE*: `LogicalAnd` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.