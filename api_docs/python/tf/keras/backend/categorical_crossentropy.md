<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.categorical_crossentropy" />
</div>

# tf.keras.backend.categorical_crossentropy

``` python
categorical_crossentropy(
    target,
    output,
    from_logits=False
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Categorical crossentropy between an output tensor and a target tensor.

#### Arguments:

* <b>`target`</b>: A tensor of the same shape as `output`.
* <b>`output`</b>: A tensor resulting from a softmax
        (unless `from_logits` is True, in which
        case `output` is expected to be the logits).
* <b>`from_logits`</b>: Boolean, whether `output` is the
        result of a softmax, or is a tensor of logits.


#### Returns:

Output tensor.