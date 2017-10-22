<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.metrics.mean_per_class_accuracy" />
</div>

# tf.metrics.mean_per_class_accuracy

``` python
mean_per_class_accuracy(
    labels,
    predictions,
    num_classes,
    weights=None,
    metrics_collections=None,
    updates_collections=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/metrics_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/metrics_impl.py).

Calculates the mean of the per-class accuracies.

Calculates the accuracy for each class, then takes the mean of that.

For estimation of the metric over a stream of data, the function creates an
`update_op` operation that updates these variables and returns the
`mean_accuracy`.

If `weights` is `None`, weights default to 1. Use weights of 0 to mask values.

#### Args:

* <b>`labels`</b>: A `Tensor` of ground truth labels with shape [batch size] and of
    type `int32` or `int64`. The tensor will be flattened if its rank > 1.
* <b>`predictions`</b>: A `Tensor` of prediction results for semantic labels, whose
    shape is [batch size] and type `int32` or `int64`. The tensor will be
    flattened if its rank > 1.
* <b>`num_classes`</b>: The possible number of labels the prediction task can
    have. This value must be provided, since a confusion matrix of
    dimension = [num_classes, num_classes] will be allocated.
* <b>`weights`</b>: Optional `Tensor` whose rank is either 0, or the same rank as
    `labels`, and must be broadcastable to `labels` (i.e., all dimensions must
    be either `1`, or the same as the corresponding `labels` dimension).
* <b>`metrics_collections`</b>: An optional list of collections that
    `mean_per_class_accuracy'
    should be added to.
* <b>`updates_collections`</b>: An optional list of collections `update_op` should be
    added to.
* <b>`name`</b>: An optional variable_scope name.


#### Returns:

* <b>`mean_accuracy`</b>: A `Tensor` representing the mean per class accuracy.
* <b>`update_op`</b>: An operation that increments the confusion matrix.


#### Raises:

* <b>`ValueError`</b>: If `predictions` and `labels` have mismatched shapes, or if
    `weights` is not `None` and its shape doesn't match `predictions`, or if
    either `metrics_collections` or `updates_collections` are not a list or
    tuple.