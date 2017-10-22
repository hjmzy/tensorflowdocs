<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.assign_add" />
</div>

# tf.assign_add

``` python
assign_add(
    ref,
    value,
    use_locking=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/state_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/state_ops.py).

See the guide: [Variables > Variable helper functions](../../../api_guides/python/state_ops.md#Variable_helper_functions)

Update 'ref' by adding 'value' to it.

This operation outputs "ref" after the update is done.
This makes it easier to chain operations that need to use the reset value.

#### Args:

* <b>`ref`</b>: A mutable `Tensor`. Must be one of the following types:
    `float32`, `float64`, `int64`, `int32`, `uint8`, `uint16`, `int16`,
    `int8`, `complex64`, `complex128`, `qint8`, `quint8`, `qint32`, `half`.
    Should be from a `Variable` node.
* <b>`value`</b>: A `Tensor`. Must have the same type as `ref`.
    The value to be added to the variable.
* <b>`use_locking`</b>: An optional `bool`. Defaults to `False`.
    If True, the addition will be protected by a lock;
    otherwise the behavior is undefined, but may exhibit less contention.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

Same as "ref".  Returned as a convenience for operations that want
to use the new value after the variable has been updated.