<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.count_nonzero" />
</div>

# tf.count_nonzero

``` python
count_nonzero(
    input_tensor,
    axis=None,
    keep_dims=False,
    dtype=tf.int64,
    name=None,
    reduction_indices=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Math > Reduction](../../../api_guides/python/math_ops.md#Reduction)

Computes number of nonzero elements across dimensions of a tensor.

Reduces `input_tensor` along the dimensions given in `axis`.
Unless `keep_dims` is true, the rank of the tensor is reduced by 1 for each
entry in `axis`. If `keep_dims` is true, the reduced dimensions
are retained with length 1.

If `axis` has no entries, all dimensions are reduced, and a
tensor with a single element is returned.

**NOTE** Floating point comparison to zero is done by exact floating point
equality check.  Small values are **not** rounded to zero for purposes of
the nonzero check.

For example:

```python
x = tf.constant([[0, 1, 0], [1, 1, 0]])
tf.count_nonzero(x)  # 3
tf.count_nonzero(x, 0)  # [1, 2, 0]
tf.count_nonzero(x, 1)  # [1, 2]
tf.count_nonzero(x, 1, keep_dims=True)  # [[1], [2]]
tf.count_nonzero(x, [0, 1])  # 3
```

#### Args:

* <b>`input_tensor`</b>: The tensor to reduce. Should be of numeric type, or `bool`.
* <b>`axis`</b>: The dimensions to reduce. If `None` (the default),
    reduces all dimensions. Must be in the range
    `[-rank(input_tensor), rank(input_tensor))`.
* <b>`keep_dims`</b>: If true, retains reduced dimensions with length 1.
* <b>`dtype`</b>: The output dtype; defaults to `tf.int64`.
* <b>`name`</b>: A name for the operation (optional).
* <b>`reduction_indices`</b>: The old (deprecated) name for axis.


#### Returns:

The reduced tensor (number of nonzero values).