<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.losses.add_loss" />
</div>

# tf.contrib.losses.add_loss

``` python
add_loss(
    loss,
    loss_collection=tf.GraphKeys.LOSSES
)
```



Defined in [`tensorflow/contrib/losses/python/losses/loss_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/losses/python/losses/loss_ops.py).

See the guide: [Losses (contrib) > Loss operations for use in neural networks.](../../../../../api_guides/python/contrib.losses.md#Loss_operations_for_use_in_neural_networks_)

Adds a externally defined loss to the collection of losses. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2016-12-30.
Instructions for updating:
Use tf.losses.add_loss instead.

#### Args:

* <b>`loss`</b>: A loss `Tensor`.
* <b>`loss_collection`</b>: Optional collection to add the loss to.