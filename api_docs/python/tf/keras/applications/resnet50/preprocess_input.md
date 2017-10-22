<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.resnet50.preprocess_input" />
</div>

# tf.keras.applications.resnet50.preprocess_input

### Aliases:

* `tf.keras.applications.resnet50.preprocess_input`
* `tf.keras.applications.vgg16.preprocess_input`
* `tf.keras.applications.vgg19.preprocess_input`

``` python
preprocess_input(
    x,
    data_format=None
)
```



Defined in [`tensorflow/python/keras/_impl/keras/applications/imagenet_utils.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/applications/imagenet_utils.py).

Preprocesses a tensor encoding a batch of images.

#### Arguments:

* <b>`x`</b>: input Numpy tensor, 4D.
* <b>`data_format`</b>: data format of the image tensor.


#### Returns:

Preprocessed tensor.