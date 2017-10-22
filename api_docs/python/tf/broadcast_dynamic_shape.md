<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.broadcast_dynamic_shape" />
</div>

# tf.broadcast_dynamic_shape

``` python
broadcast_dynamic_shape(
    shape_x,
    shape_y
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/array_ops.py).

See the guide: [Tensor Transformations > Shapes and Shaping](../../../api_guides/python/array_ops.md#Shapes_and_Shaping)

Returns the broadcasted dynamic shape between `shape_x` and `shape_y`.

#### Args:

* <b>`shape_x`</b>: A rank 1 integer `Tensor`, representing the shape of x.
* <b>`shape_y`</b>: A rank 1 integer `Tensor`, representing the shape of y.


#### Returns:

A rank 1 integer `Tensor` representing the broadcasted shape.