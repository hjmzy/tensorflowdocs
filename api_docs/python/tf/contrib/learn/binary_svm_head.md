<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.learn.binary_svm_head" />
</div>

# tf.contrib.learn.binary_svm_head

``` python
binary_svm_head(
    label_name=None,
    weight_column_name=None,
    enable_centered_bias=False,
    head_name=None,
    thresholds=None
)
```



Defined in [`tensorflow/contrib/learn/python/learn/estimators/head.py`](https://www.tensorflow.org/code/tensorflow/contrib/learn/python/learn/estimators/head.py).

Creates a `Head` for binary classification with SVMs.

The head uses binary hinge loss.

#### Args:

* <b>`label_name`</b>: String, name of the key in label dict. Can be null if label
    is a tensor (single headed models).
* <b>`weight_column_name`</b>: A string defining feature column name representing
    weights. It is used to down weight or boost examples during training. It
    will be multiplied by the loss of the example.
* <b>`enable_centered_bias`</b>: A bool. If True, estimator will learn a centered
    bias variable for each class. Rest of the model structure learns the
    residual after centered bias.
* <b>`head_name`</b>: name of the head. If provided, predictions, summary and metrics
    keys will be suffixed by `"/" + head_name` and the default variable scope
    will be `head_name`.
* <b>`thresholds`</b>: thresholds for eval metrics, defaults to [.5]


#### Returns:

An instance of `Head` for binary classification with SVM.