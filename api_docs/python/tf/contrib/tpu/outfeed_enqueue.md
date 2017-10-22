<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.outfeed_enqueue" />
</div>

# tf.contrib.tpu.outfeed_enqueue

``` python
outfeed_enqueue(
    input,
    name=None
)
```



Defined in `tensorflow/contrib/tpu/ops/gen_tpu_ops.py`.

An op which emits a single Tensor value from an XLA computation.

#### Args:

* <b>`input`</b>: A `Tensor`. A tensor that will be inserted into the outfeed queue.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The created Operation.