<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.InceptionV3" />
</div>

# tf.keras.applications.InceptionV3

### Aliases:

* `tf.keras.applications.InceptionV3`
* `tf.keras.applications.inception_v3.InceptionV3`

``` python
InceptionV3(
    include_top=True,
    weights='imagenet',
    input_tensor=None,
    input_shape=None,
    pooling=None,
    classes=1000
)
```



Defined in [`tensorflow/python/keras/_impl/keras/applications/inception_v3.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/applications/inception_v3.py).

Instantiates the Inception v3 architecture.

Optionally loads weights pre-trained
on ImageNet. Note that when using TensorFlow,
for best performance you should set
`image_data_format="channels_last"` in your Keras config
at ~/.keras/keras.json.
The model and the weights are compatible with both
TensorFlow and Theano. The data format
convention used by the model is the one
specified in your Keras config file.
Note that the default input image size for this model is 299x299.

#### Arguments:

* <b>`include_top`</b>: whether to include the fully-connected
        layer at the top of the network.
* <b>`weights`</b>: one of `None` (random initialization)
        or "imagenet" (pre-training on ImageNet).
* <b>`input_tensor`</b>: optional Keras tensor (i.e. output of `layers.Input()`)
        to use as image input for the model.
* <b>`input_shape`</b>: optional shape tuple, only to be specified
        if `include_top` is False (otherwise the input shape
        has to be `(299, 299, 3)` (with `channels_last` data format)
        or `(3, 299, 299)` (with `channels_first` data format).
        It should have exactly 3 input channels,
        and width and height should be no smaller than 139.
        E.g. `(150, 150, 3)` would be one valid value.
* <b>`pooling`</b>: Optional pooling mode for feature extraction
        when `include_top` is `False`.
        - `None` means that the output of the model will be
            the 4D tensor output of the
            last convolutional layer.
        - `avg` means that global average pooling
            will be applied to the output of the
            last convolutional layer, and thus
            the output of the model will be a 2D tensor.
        - `max` means that global max pooling will
            be applied.
* <b>`classes`</b>: optional number of classes to classify images
        into, only to be specified if `include_top` is True, and
        if no `weights` argument is specified.


#### Returns:

A Keras model instance.


#### Raises:

* <b>`ValueError`</b>: in case of invalid argument for `weights`,
        or invalid input shape.