<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.temporal_padding" />
</div>

# tf.keras.backend.temporal_padding

``` python
temporal_padding(
    x,
    padding=(1, 1)
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Pads the middle dimension of a 3D tensor.

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`padding`</b>: Tuple of 2 integers, how many zeros to
        add at the start and end of dim 1.


#### Returns:

A padded 3D tensor.