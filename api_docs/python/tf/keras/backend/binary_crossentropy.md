<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.binary_crossentropy" />
</div>

# tf.keras.backend.binary_crossentropy

``` python
binary_crossentropy(
    target,
    output,
    from_logits=False
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Binary crossentropy between an output tensor and a target tensor.

#### Arguments:

* <b>`target`</b>: A tensor with the same shape as `output`.
* <b>`output`</b>: A tensor.
* <b>`from_logits`</b>: Whether `output` is expected to be a logits tensor.
        By default, we consider that `output`
        encodes a probability distribution.


#### Returns:

A tensor.