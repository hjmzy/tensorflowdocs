<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random_normal" />
</div>

# tf.random_normal

``` python
random_normal(
    shape,
    mean=0.0,
    stddev=1.0,
    dtype=tf.float32,
    seed=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/random_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/random_ops.py).

See the guide: [Constants, Sequences, and Random Values > Random Tensors](../../../api_guides/python/constant_op.md#Random_Tensors)

Outputs random values from a normal distribution.

#### Args:

* <b>`shape`</b>: A 1-D integer Tensor or Python array. The shape of the output tensor.
* <b>`mean`</b>: A 0-D Tensor or Python value of type `dtype`. The mean of the normal
    distribution.
* <b>`stddev`</b>: A 0-D Tensor or Python value of type `dtype`. The standard deviation
    of the normal distribution.
* <b>`dtype`</b>: The type of the output.
* <b>`seed`</b>: A Python integer. Used to create a random seed for the distribution.
    See
    [`tf.set_random_seed`](../tf/set_random_seed.md)
    for behavior.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A tensor of the specified shape filled with random normal values.