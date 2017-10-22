<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.models.model_from_json" />
</div>

# tf.keras.models.model_from_json

``` python
model_from_json(
    json_string,
    custom_objects=None
)
```



Defined in [`tensorflow/python/keras/_impl/keras/models.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/models.py).

Parses a JSON model configuration file and returns a model instance.

#### Arguments:

* <b>`json_string`</b>: JSON string encoding a model configuration.
* <b>`custom_objects`</b>: Optional dictionary mapping names
        (strings) to custom classes or functions to be
        considered during deserialization.


#### Returns:

A Keras model instance (uncompiled).