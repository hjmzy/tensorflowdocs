<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.softmax" />
</div>

# tf.nn.softmax

``` python
softmax(
    logits,
    dim=-1,
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/nn_ops.py).

See the guides: [Layers (contrib) > Higher level ops for building neural network layers](../../../../api_guides/python/contrib.layers.md#Higher_level_ops_for_building_neural_network_layers), [Neural Network > Classification](../../../../api_guides/python/nn.md#Classification)

Computes softmax activations.

This function performs the equivalent of

    softmax = tf.exp(logits) / tf.reduce_sum(tf.exp(logits), dim)

#### Args:

* <b>`logits`</b>: A non-empty `Tensor`. Must be one of the following types: `half`,
    `float32`, `float64`.
* <b>`dim`</b>: The dimension softmax would be performed on. The default is -1 which
    indicates the last dimension.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type and shape as `logits`.


#### Raises:

* <b>`InvalidArgumentError`</b>: if `logits` is empty or `dim` is beyond the last
    dimension of `logits`.