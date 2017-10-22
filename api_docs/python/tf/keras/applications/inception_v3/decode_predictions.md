<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.applications.inception_v3.decode_predictions" />
</div>

# tf.keras.applications.inception_v3.decode_predictions

### Aliases:

* `tf.keras.applications.inception_v3.decode_predictions`
* `tf.keras.applications.mobilenet.decode_predictions`
* `tf.keras.applications.resnet50.decode_predictions`
* `tf.keras.applications.vgg16.decode_predictions`
* `tf.keras.applications.vgg19.decode_predictions`
* `tf.keras.applications.xception.decode_predictions`

``` python
decode_predictions(
    preds,
    top=5
)
```



Defined in [`tensorflow/python/keras/_impl/keras/applications/imagenet_utils.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/applications/imagenet_utils.py).

Decodes the prediction of an ImageNet model.

#### Arguments:

* <b>`preds`</b>: Numpy tensor encoding a batch of predictions.
* <b>`top`</b>: integer, how many top-guesses to return.


#### Returns:

A list of lists of top class prediction tuples
`(class_name, class_description, score)`.
One list of tuples per sample in batch input.


#### Raises:

* <b>`ValueError`</b>: in case of invalid shape of the `pred` array
        (must be 2D).