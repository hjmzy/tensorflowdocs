<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.weighted_moments" />
</div>

# tf.nn.weighted_moments

``` python
weighted_moments(
    x,
    axes,
    frequency_weights,
    name=None,
    keep_dims=False
)
```



Defined in [`tensorflow/python/ops/nn_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/nn_impl.py).

See the guide: [Neural Network > Normalization](../../../../api_guides/python/nn.md#Normalization)

Returns the frequency-weighted mean and variance of `x`.

#### Args:

* <b>`x`</b>: A tensor.
* <b>`axes`</b>: 1-d tensor of int32 values; these are the axes along which
    to compute mean and variance.
* <b>`frequency_weights`</b>: A tensor of positive weights which can be
    broadcast with x.
* <b>`name`</b>: Name used to scope the operation.
* <b>`keep_dims`</b>: Produce moments with the same dimensionality as the input.


#### Returns:

Two tensors: `weighted_mean` and `weighted_variance`.