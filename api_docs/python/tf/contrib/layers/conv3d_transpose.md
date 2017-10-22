<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.conv3d_transpose" />
</div>

# tf.contrib.layers.conv3d_transpose

### Aliases:

* `tf.contrib.layers.conv3d_transpose`
* `tf.contrib.layers.convolution3d_transpose`

``` python
conv3d_transpose(
    inputs,
    num_outputs,
    kernel_size,
    stride=1,
    padding='SAME',
    data_format=DATA_FORMAT_NDHWC,
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

Adds a convolution3d_transpose with an optional batch normalization layer.

The function creates a variable called `weights`, representing the
kernel, that is convolved with the input. If `batch_norm_params` is `None`, a
second variable called 'biases' is added to the result of the operation.
#### Args:

* <b>`inputs`</b>: A 5-D `Tensor` of type `float` and shape
    `[batch, depth, height, width, in_channels]` for `NDHWC` data format or
    `[batch, in_channels, depth, height, width]` for `NCDHW` data format.
* <b>`num_outputs`</b>: Integer, the number of output filters.
* <b>`kernel_size`</b>: A list of length 3 holding the [kernel_depth, kernel_height,
    kernel_width] of the filters. Can be an int if both values are the same.
* <b>`stride`</b>: A list of length 3: [stride_depth, stride_height, stride_width].
    Can be an int if both strides are the same.  Note that presently
    both strides must have the same value.
* <b>`padding`</b>: One of 'VALID' or 'SAME'.
* <b>`data_format`</b>: A string. `NDHWC` (default) and `NCDHW` are supported.
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
    a dictionary containing a different list of collection per variable.
* <b>`outputs_collections`</b>: Collection to add the outputs.
* <b>`trainable`</b>: Whether or not the variables should be trainable or not.
* <b>`scope`</b>: Optional scope for variable_scope.

#### Returns:

A tensor representing the output of the operation.

#### Raises:

* <b>`ValueError`</b>: If 'kernel_size' is not a list of length 3.
* <b>`ValueError`</b>: If `data_format` is neither `NDHWC` nor `NCDHW`.
* <b>`ValueError`</b>: If `C` dimension of `inputs` is None.