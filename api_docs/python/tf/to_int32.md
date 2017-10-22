<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.to_int32" />
</div>

# tf.to_int32

``` python
to_int32(
    x,
    name='ToInt32'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Tensor Transformations > Casting](../../../api_guides/python/array_ops.md#Casting)

Casts a tensor to type `int32`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` with same shape as `x` with type `int32`.


#### Raises:

* <b>`TypeError`</b>: If `x` cannot be cast to the `int32`.