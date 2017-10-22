<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.glorot_uniform_initializer" />
</div>

# tf.glorot_uniform_initializer

``` python
glorot_uniform_initializer(
    seed=None,
    dtype=tf.float32
)
```



Defined in [`tensorflow/python/ops/init_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/init_ops.py).

The Glorot uniform initializer, also called Xavier uniform initializer.

It draws samples from a uniform distribution within [-limit, limit]
where `limit` is `sqrt(6 / (fan_in + fan_out))`
where `fan_in` is the number of input units in the weight tensor
and `fan_out` is the number of output units in the weight tensor.

Reference: http://jmlr.org/proceedings/papers/v9/glorot10a/glorot10a.pdf

#### Args:

* <b>`seed`</b>: A Python integer. Used to create random seeds. See
    [`tf.set_random_seed`](../tf/set_random_seed.md)
    for behavior.
* <b>`dtype`</b>: The data type. Only floating point types are supported.


#### Returns:

An initializer.