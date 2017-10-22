<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.elu" />
</div>

# tf.nn.elu

``` python
elu(
    features,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_nn_ops.py`.

See the guide: [Neural Network > Activation Functions](../../../../api_guides/python/nn.md#Activation_Functions)

Computes exponential linear: `exp(features) - 1` if < 0, `features` otherwise.

See [Fast and Accurate Deep Network Learning by Exponential Linear Units (ELUs)
](http://arxiv.org/abs/1511.07289)

#### Args:

* <b>`features`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `features`.