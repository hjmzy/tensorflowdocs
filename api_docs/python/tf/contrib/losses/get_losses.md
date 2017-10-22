<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.losses.get_losses" />
</div>

# tf.contrib.losses.get_losses

``` python
get_losses(
    scope=None,
    loss_collection=tf.GraphKeys.LOSSES
)
```



Defined in [`tensorflow/contrib/losses/python/losses/loss_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/losses/python/losses/loss_ops.py).

See the guide: [Losses (contrib) > Loss operations for use in neural networks.](../../../../../api_guides/python/contrib.losses.md#Loss_operations_for_use_in_neural_networks_)

Gets the list of losses from the loss_collection. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2016-12-30.
Instructions for updating:
Use tf.losses.get_losses instead.

#### Args:

* <b>`scope`</b>: an optional scope for filtering the losses to return.
* <b>`loss_collection`</b>: Optional losses collection.


#### Returns:

a list of loss tensors.