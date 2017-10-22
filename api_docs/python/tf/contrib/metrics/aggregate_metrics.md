<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.metrics.aggregate_metrics" />
</div>

# tf.contrib.metrics.aggregate_metrics

``` python
aggregate_metrics(*value_update_tuples)
```



Defined in [`tensorflow/contrib/metrics/python/ops/metric_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/metrics/python/ops/metric_ops.py).

See the guide: [Metrics (contrib) > Metric `Ops`](../../../../../api_guides/python/contrib.metrics.md#Metric_Ops_)

Aggregates the metric value tensors and update ops into two lists.

#### Args:

* <b>`*value_update_tuples`</b>: a variable number of tuples, each of which contain the
    pair of (value_tensor, update_op) from a streaming metric.


#### Returns:

A list of value `Tensor` objects and a list of update ops.


#### Raises:

* <b>`ValueError`</b>: if `value_update_tuples` is empty.