<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.outfeed_enqueue_tuple" />
</div>

# tf.contrib.tpu.outfeed_enqueue_tuple

``` python
outfeed_enqueue_tuple(
    inputs,
    name=None
)
```



Defined in `tensorflow/contrib/tpu/ops/gen_tpu_ops.py`.

An op which emits multiple Tensor values from an XLA computation.

#### Args:

* <b>`inputs`</b>: A list of `Tensor` objects.
    A list of tensors that will be inserted into the outfeed queue as an
    XLA tuple.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The created Operation.