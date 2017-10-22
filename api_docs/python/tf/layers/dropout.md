<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.layers.dropout" />
</div>

# tf.layers.dropout

``` python
dropout(
    inputs,
    rate=0.5,
    noise_shape=None,
    seed=None,
    training=False,
    name=None
)
```



Defined in [`tensorflow/python/layers/core.py`](https://www.tensorflow.org/code/tensorflow/python/layers/core.py).

See the guide: [Reading data > Multiple input pipelines](../../../../api_guides/python/reading_data.md#Multiple_input_pipelines)

Applies Dropout to the input.

Dropout consists in randomly setting a fraction `rate` of input units to 0
at each update during training time, which helps prevent overfitting.
The units that are kept are scaled by `1 / (1 - rate)`, so that their
sum is unchanged at training time and inference time.

#### Arguments:

* <b>`inputs`</b>: Tensor input.
* <b>`rate`</b>: The dropout rate, between 0 and 1. E.g. "rate=0.1" would drop out
    10% of input units.
* <b>`noise_shape`</b>: 1D tensor of type `int32` representing the shape of the
    binary dropout mask that will be multiplied with the input.
    For instance, if your inputs have shape
    `(batch_size, timesteps, features)`, and you want the dropout mask
    to be the same for all timesteps, you can use
    `noise_shape=[batch_size, 1, features]`.
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
    [`tf.set_random_seed`](../../tf/set_random_seed.md)
    for behavior.
* <b>`training`</b>: Either a Python boolean, or a TensorFlow boolean scalar tensor
    (e.g. a placeholder). Whether to return the output in training mode
    (apply dropout) or in inference mode (return the input untouched).
* <b>`name`</b>: The name of the layer (string).


#### Returns:

Output tensor.