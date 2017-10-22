<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.signal.hamming_window" />
</div>

# tf.contrib.signal.hamming_window

``` python
hamming_window(
    window_length,
    periodic=True,
    dtype=tf.float32,
    name=None
)
```



Defined in [`tensorflow/contrib/signal/python/ops/window_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/signal/python/ops/window_ops.py).

See the guide: [Signal Processing (contrib) > Reconstructing framed sequences and applying a tapering window](../../../../../api_guides/python/contrib.signal.md#Reconstructing_framed_sequences_and_applying_a_tapering_window)

Generate a [Hamming][hamming] window.

#### Args:

* <b>`window_length`</b>: A scalar `Tensor` indicating the window length to generate.
* <b>`periodic`</b>: A bool `Tensor` indicating whether to generate a periodic or
    symmetric window. Periodic windows are typically used for spectral
    analysis while symmetric windows are typically used for digital
    filter design.
* <b>`dtype`</b>: The data type to produce. Must be a floating point type.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `Tensor` of shape `[window_length]` of type `dtype`.


#### Raises:

* <b>`ValueError`</b>: If `dtype` is not a floating point type.

[hamming]: https://en.wikipedia.org/wiki/Window_function#Hamming_window