<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.to_int64" />
</div>

# tf.to_int64

``` python
to_int64(
    x,
    name='ToInt64'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Tensor Transformations > Casting](../../../api_guides/python/array_ops.md#Casting)

Casts a tensor to type `int64`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` with same shape as `x` with type `int64`.


#### Raises:

* <b>`TypeError`</b>: If `x` cannot be cast to the `int64`.