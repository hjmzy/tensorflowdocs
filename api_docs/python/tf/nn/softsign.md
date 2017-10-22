<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.softsign" />
</div>

# tf.nn.softsign

``` python
softsign(
    features,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_nn_ops.py`.

See the guide: [Neural Network > Activation Functions](../../../../api_guides/python/nn.md#Activation_Functions)

Computes softsign: `features / (abs(features) + 1)`.

#### Args:

* <b>`features`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `int64`, `uint8`, `int16`, `int8`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `features`.