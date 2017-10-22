<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.remove_squeezable_dimensions" />
</div>

# tf.contrib.framework.remove_squeezable_dimensions

``` python
remove_squeezable_dimensions(
    predictions,
    labels,
    name=None
)
```



Defined in [`tensorflow/contrib/framework/python/framework/tensor_util.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/framework/tensor_util.py).

See the guide: [Framework (contrib)](../../../../../api_guides/python/contrib.framework.md)

Squeeze last dim if ranks of `predictions` and `labels` differ by 1. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Please switch to tf.confusion_matrix.remove_squeezable_dimensions.Note that order of the inputs and outputs of labels and predictions have also been switched.

This will use static shape if available. Otherwise, it will add graph
operations, which could result in a performance hit.

#### Args:

* <b>`predictions`</b>: Predicted values, a `Tensor` of arbitrary dimensions.
* <b>`labels`</b>: Label values, a `Tensor` whose dimensions match `predictions`.
* <b>`name`</b>: Name of the op.


#### Returns:

Tuple of `predictions` and `labels`, possibly with last dim squeezed.