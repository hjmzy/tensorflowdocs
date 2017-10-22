<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.get_summary_description" />
</div>

# tf.summary.get_summary_description

``` python
get_summary_description(node_def)
```



Defined in [`tensorflow/python/summary/summary.py`](https://www.tensorflow.org/code/tensorflow/python/summary/summary.py).

See the guide: [Summary Operations > Utilities](../../../../api_guides/python/summary.md#Utilities)

Given a TensorSummary node_def, retrieve its SummaryDescription.

When a Summary op is instantiated, a SummaryDescription of associated
metadata is stored in its NodeDef. This method retrieves the description.

#### Args:

* <b>`node_def`</b>: the node_def_pb2.NodeDef of a TensorSummary op


#### Returns:

a summary_pb2.SummaryDescription


#### Raises:

* <b>`ValueError`</b>: if the node is not a summary op.