<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.get_losses" />
</div>

# tf.losses.get_losses

``` python
get_losses(
    scope=None,
    loss_collection=tf.GraphKeys.LOSSES
)
```



Defined in [`tensorflow/python/ops/losses/util.py`](https://www.tensorflow.org/code/tensorflow/python/ops/losses/util.py).

Gets the list of losses from the loss_collection.

#### Args:

* <b>`scope`</b>: An optional scope name for filtering the losses to return.
* <b>`loss_collection`</b>: Optional losses collection.


#### Returns:

a list of loss tensors.