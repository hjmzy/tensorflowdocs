<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.relu6" />
</div>

# tf.nn.relu6

``` python
relu6(
    features,
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/nn_ops.py).

See the guides: [Layers (contrib) > Higher level ops for building neural network layers](../../../../api_guides/python/contrib.layers.md#Higher_level_ops_for_building_neural_network_layers), [Neural Network > Activation Functions](../../../../api_guides/python/nn.md#Activation_Functions)

Computes Rectified Linear 6: `min(max(features, 0), 6)`.
Source: [Convolutional Deep Belief Networks on CIFAR-10. A. Krizhevsky](http://www.cs.utoronto.ca/~kriz/conv-cifar10-aug2010.pdf)

#### Args:

* <b>`features`</b>: A `Tensor` with type `float`, `double`, `int32`, `int64`, `uint8`,
    `int16`, or `int8`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` with the same type as `features`.