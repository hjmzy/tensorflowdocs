<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.metrics.streaming_false_negative_rate_at_thresholds" />
</div>

# tf.contrib.metrics.streaming_false_negative_rate_at_thresholds

``` python
streaming_false_negative_rate_at_thresholds(
    predictions,
    labels,
    thresholds,
    weights=None,
    metrics_collections=None,
    updates_collections=None,
    name=None
)
```



Defined in [`tensorflow/contrib/metrics/python/ops/metric_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/metrics/python/ops/metric_ops.py).

Computes various fnr values for different `thresholds` on `predictions`.

The `streaming_false_negative_rate_at_thresholds` function creates two
local variables, `false_negatives`, `true_positives`, for various values of
thresholds. `false_negative_rate[i]` is defined as the total weight
of values in `predictions` above `thresholds[i]` whose corresponding entry in
`labels` is `False`, divided by the total weight of `True` values in `labels`
(`false_negatives[i] / (false_negatives[i] + true_positives[i])`).

For estimation of the metric over a stream of data, the function creates an
`update_op` operation that updates these variables and returns the
`false_positive_rate`.

If `weights` is `None`, weights default to 1. Use weights of 0 to mask values.

#### Args:

* <b>`predictions`</b>: A floating point `Tensor` of arbitrary shape and whose values
    are in the range `[0, 1]`.
* <b>`labels`</b>: A `bool` `Tensor` whose shape matches `predictions`.
* <b>`thresholds`</b>: A python list or tuple of float thresholds in `[0, 1]`.
* <b>`weights`</b>: `Tensor` whose rank is either 0, or the same rank as `labels`, and
    must be broadcastable to `labels` (i.e., all dimensions must be either
    `1`, or the same as the corresponding `labels` dimension).
* <b>`metrics_collections`</b>: An optional list of collections that
    `false_negative_rate` should be added to.
* <b>`updates_collections`</b>: An optional list of collections that `update_op` should
    be added to.
* <b>`name`</b>: An optional variable_scope name.


#### Returns:

* <b>`false_negative_rate`</b>: A float `Tensor` of shape `[len(thresholds)]`.
* <b>`update_op`</b>: An operation that increments the `false_negatives` and
    `true_positives` variables that are used in the computation of
    `false_negative_rate`.


#### Raises:

* <b>`ValueError`</b>: If `predictions` and `labels` have mismatched shapes, or if
    `weights` is not `None` and its shape doesn't match `predictions`, or if
    either `metrics_collections` or `updates_collections` are not a list or
    tuple.