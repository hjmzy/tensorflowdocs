<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.is_inf" />
</div>

# tf.is_inf

``` python
is_inf(
    x,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_math_ops.py`.

See the guide: [Control Flow > Debugging Operations](../../../api_guides/python/control_flow_ops.md#Debugging_Operations)

Returns which elements of x are Inf.



#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

#### numpy compatibility
Equivalent to np.isinf

