<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.conv1d" />
</div>

# tf.keras.backend.conv1d

``` python
conv1d(
    x,
    kernel,
    strides=1,
    padding='valid',
    data_format=None,
    dilation_rate=1
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

1D convolution.

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`kernel`</b>: kernel tensor.
* <b>`strides`</b>: stride integer.
* <b>`padding`</b>: string, `"same"`, `"causal"` or `"valid"`.
* <b>`data_format`</b>: string, one of "channels_last", "channels_first".
* <b>`dilation_rate`</b>: integer dilate rate.


#### Returns:

A tensor, result of 1D convolution.