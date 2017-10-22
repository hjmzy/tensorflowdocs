<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.fully_connected" />
</div>

# tf.contrib.layers.fully_connected

``` python
fully_connected(
    inputs,
    num_outputs,
    activation_fn=tf.nn.relu,
    normalizer_fn=None,
    normalizer_params=None,
    weights_initializer=initializers.xavier_initializer(),
    weights_regularizer=None,
    biases_initializer=tf.zeros_initializer(),
    biases_regularizer=None,
    reuse=None,
    variables_collections=None,
    outputs_collections=None,
    trainable=True,
    scope=None
)
```



Defined in [`tensorflow/contrib/layers/python/layers/layers.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/layers.py).

See the guide: [Layers (contrib) > Higher level ops for building neural network layers](../../../../../api_guides/python/contrib.layers.md#Higher_level_ops_for_building_neural_network_layers)

Adds a fully connected layer.

`fully_connected` creates a variable called `weights`, representing a fully
connected weight matrix, which is multiplied by the `inputs` to produce a
`Tensor` of hidden units. If a `normalizer_fn` is provided (such as
`batch_norm`), it is then applied. Otherwise, if `normalizer_fn` is
None and a `biases_initializer` is provided then a `biases` variable would be
created and added the hidden units. Finally, if `activation_fn` is not `None`,
it is applied to the hidden units as well.

Note: that if `inputs` have a rank greater than 2, then `inputs` is flattened
prior to the initial matrix multiply by `weights`.

#### Args:

* <b>`inputs`</b>: A tensor of at least rank 2 and static value for the last dimension;
    i.e. `[batch_size, depth]`, `[None, None, None, channels]`.
* <b>`num_outputs`</b>: Integer or long, the number of output units in the layer.
* <b>`activation_fn`</b>: Activation function. The default value is a ReLU function.
    Explicitly set it to None to skip it and maintain a linear activation.
* <b>`normalizer_fn`</b>: Normalization function to use instead of `biases`. If
    `normalizer_fn` is provided then `biases_initializer` and
    `biases_regularizer` are ignored and `biases` are not created nor added.
    default set to None for no normalizer function
* <b>`normalizer_params`</b>: Normalization function parameters.
* <b>`weights_initializer`</b>: An initializer for the weights.
* <b>`weights_regularizer`</b>: Optional regularizer for the weights.
* <b>`biases_initializer`</b>: An initializer for the biases. If None skip biases.
* <b>`biases_regularizer`</b>: Optional regularizer for the biases.
* <b>`reuse`</b>: Whether or not the layer and its variables should be reused. To be
    able to reuse the layer scope must be given.
* <b>`variables_collections`</b>: Optional list of collections for all the variables or
    a dictionary containing a different list of collections per variable.
* <b>`outputs_collections`</b>: Collection to add the outputs.
* <b>`trainable`</b>: If `True` also add variables to the graph collection
    `GraphKeys.TRAINABLE_VARIABLES` (see tf.Variable).
* <b>`scope`</b>: Optional scope for variable_scope.


#### Returns:

The tensor variable representing the result of the series of operations.


#### Raises:

* <b>`ValueError`</b>: If x has rank less than 2 or if its last dimension is not set.