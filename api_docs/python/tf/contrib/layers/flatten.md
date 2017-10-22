<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.flatten" />
</div>

# tf.contrib.layers.flatten

``` python
flatten(
    inputs,
    outputs_collections=None,
    scope=None
)
```



Defined in [`tensorflow/contrib/layers/python/layers/layers.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/layers.py).

See the guide: [Layers (contrib) > Higher level ops for building neural network layers](../../../../../api_guides/python/contrib.layers.md#Higher_level_ops_for_building_neural_network_layers)

Flattens the input while maintaining the batch_size.

  Assumes that the first dimension represents the batch.

#### Args:

* <b>`inputs`</b>: A tensor of size [batch_size, ...].
* <b>`outputs_collections`</b>: Collection to add the outputs.
* <b>`scope`</b>: Optional scope for name_scope.


#### Returns:

A flattened tensor with shape [batch_size, k].

#### Raises:

* <b>`ValueError`</b>: If inputs rank is unknown or less than 2.