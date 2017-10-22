<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.split" />
</div>

# tf.split

``` python
split(
    value,
    num_or_size_splits,
    axis=0,
    num=None,
    name='split'
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/array_ops.py).

See the guide: [Tensor Transformations > Slicing and Joining](../../../api_guides/python/array_ops.md#Slicing_and_Joining)

Splits a tensor into sub tensors.

If `num_or_size_splits` is an integer type, `num_split`, then splits `value`
along dimension `axis` into `num_split` smaller tensors.
Requires that `num_split` evenly divides `value.shape[axis]`.

If `num_or_size_splits` is not an integer type, it is presumed to be a Tensor
`size_splits`, then splits `value` into `len(size_splits)` pieces. The shape
of the `i`-th piece has the same size as the `value` except along dimension
`axis` where the size is `size_splits[i]`.

For example:

```python
# 'value' is a tensor with shape [5, 30]
# Split 'value' into 3 tensors with sizes [4, 15, 11] along dimension 1
split0, split1, split2 = tf.split(value, [4, 15, 11], 1)
tf.shape(split0)  # [5, 4]
tf.shape(split1)  # [5, 15]
tf.shape(split2)  # [5, 11]
# Split 'value' into 3 tensors along dimension 1
split0, split1, split2 = tf.split(value, num_or_size_splits=3, axis=1)
tf.shape(split0)  # [5, 10]
```

#### Args:

* <b>`value`</b>: The `Tensor` to split.
* <b>`num_or_size_splits`</b>: Either a 0-D integer `Tensor` indicating the number of
    splits along split_dim or a 1-D integer `Tensor` integer tensor containing
    the sizes of each output tensor along split_dim. If a scalar then it must
    evenly divide `value.shape[axis]`; otherwise the sum of sizes along the
    split dimension must match that of the `value`.
* <b>`axis`</b>: A 0-D `int32` `Tensor`. The dimension along which to split.
    Must be in the range `[-rank(value), rank(value))`. Defaults to 0.
* <b>`num`</b>: Optional, used to specify the number of outputs when it cannot be
    inferred from the shape of `size_splits`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

if `num_or_size_splits` is a scalar returns `num_or_size_splits` `Tensor`
objects; if `num_or_size_splits` is a 1-D Tensor returns
`num_or_size_splits.get_shape[0]` `Tensor` objects resulting from splitting
`value`.


#### Raises:

* <b>`ValueError`</b>: If `num` is unspecified and cannot be inferred.