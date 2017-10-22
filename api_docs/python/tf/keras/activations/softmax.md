<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.softmax" />
</div>

# tf.keras.activations.softmax

``` python
softmax(
    x,
    axis=-1
)
```



Defined in [`tensorflow/python/keras/_impl/keras/activations.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/activations.py).

Softmax activation function.

#### Arguments:

* <b>`x `</b>: Tensor.
* <b>`axis`</b>: Integer, axis along which the softmax normalization is applied.


#### Returns:

Tensor, output of softmax transformation.


#### Raises:

* <b>`ValueError`</b>: In case `dim(x) == 1`.