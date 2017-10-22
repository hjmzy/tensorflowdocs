<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.layers.max_pooling2d" />
</div>

# tf.layers.max_pooling2d

``` python
max_pooling2d(
    inputs,
    pool_size,
    strides,
    padding='valid',
    data_format='channels_last',
    name=None
)
```



Defined in [`tensorflow/python/layers/pooling.py`](https://www.tensorflow.org/code/tensorflow/python/layers/pooling.py).

Max pooling layer for 2D inputs (e.g. images).

#### Arguments:

* <b>`inputs`</b>: The tensor over which to pool. Must have rank 4.
* <b>`pool_size`</b>: An integer or tuple/list of 2 integers: (pool_height, pool_width)
    specifying the size of the pooling window.
    Can be a single integer to specify the same value for
    all spatial dimensions.
* <b>`strides`</b>: An integer or tuple/list of 2 integers,
    specifying the strides of the pooling operation.
    Can be a single integer to specify the same value for
    all spatial dimensions.
* <b>`padding`</b>: A string. The padding method, either 'valid' or 'same'.
    Case-insensitive.
* <b>`data_format`</b>: A string. The ordering of the dimensions in the inputs.
    `channels_last` (default) and `channels_first` are supported.
    `channels_last` corresponds to inputs with shape
    `(batch, height, width, channels)` while `channels_first` corresponds to
    inputs with shape `(batch, channels, height, width)`.
* <b>`name`</b>: A string, the name of the layer.


#### Returns:

Output tensor.