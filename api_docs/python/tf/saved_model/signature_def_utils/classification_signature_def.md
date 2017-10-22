<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.signature_def_utils.classification_signature_def" />
</div>

# tf.saved_model.signature_def_utils.classification_signature_def

``` python
classification_signature_def(
    examples,
    classes,
    scores
)
```



Defined in [`tensorflow/python/saved_model/signature_def_utils_impl.py`](https://www.tensorflow.org/code/tensorflow/python/saved_model/signature_def_utils_impl.py).

Creates classification signature from given examples and predictions.

This function produces signatures intended for use with the TensorFlow Serving
Classify API (tensorflow_serving/apis/prediction_service.proto), and so
constrains the input and output types to those allowed by TensorFlow Serving.

#### Args:

* <b>`examples`</b>: A string `Tensor`, expected to accept serialized tf.Examples.
* <b>`classes`</b>: A string `Tensor`.  Note that the ClassificationResponse message
    requires that class labels are strings, not integers or anything else.
* <b>`scores`</b>: a float `Tensor`.


#### Returns:

A classification-flavored signature_def.


#### Raises:

* <b>`ValueError`</b>: If examples is `None`.