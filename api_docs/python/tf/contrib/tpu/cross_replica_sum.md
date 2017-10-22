<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.cross_replica_sum" />
</div>

# tf.contrib.tpu.cross_replica_sum

``` python
cross_replica_sum(
    input,
    name=None
)
```



Defined in `tensorflow/contrib/tpu/ops/gen_tpu_ops.py`.

An Op to sum inputs across replicated TPU instances. Each

instance supplies its own input, and the output of each is the sum of
all the inputs.

#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float32`.
    The local input to the sum.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.
The sum of all the distributed inputs.