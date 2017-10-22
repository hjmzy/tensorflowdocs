<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.shape_n" />
</div>

# tf.shape_n

``` python
shape_n(
    input,
    out_type=tf.int32,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_array_ops.py`.

See the guide: [Tensor Transformations > Shapes and Shaping](../../../api_guides/python/array_ops.md#Shapes_and_Shaping)

Returns shape of tensors.

This operation returns N 1-D integer tensors representing shape of `input[i]s`.

#### Args:

* <b>`input`</b>: A list of at least 1 `Tensor` objects with the same type.
* <b>`out_type`</b>: An optional `tf.DType` from: `tf.int32, tf.int64`. Defaults to `tf.int32`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A list with the same length as `input` of `Tensor` objects with type `out_type`.