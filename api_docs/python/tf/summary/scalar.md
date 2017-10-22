<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.scalar" />
</div>

# tf.summary.scalar

``` python
scalar(
    name,
    tensor,
    collections=None,
    family=None
)
```



Defined in [`tensorflow/python/summary/summary.py`](https://www.tensorflow.org/code/tensorflow/python/summary/summary.py).

See the guide: [Summary Operations > Generation of Summaries](../../../../api_guides/python/summary.md#Generation_of_Summaries)

Outputs a `Summary` protocol buffer containing a single scalar value.

The generated Summary has a Tensor.proto containing the input Tensor.

#### Args:

* <b>`name`</b>: A name for the generated node. Will also serve as the series name in
    TensorBoard.
* <b>`tensor`</b>: A real numeric Tensor containing a single value.
* <b>`collections`</b>: Optional list of graph collections keys. The new summary op is
    added to these collections. Defaults to `[GraphKeys.SUMMARIES]`.
* <b>`family`</b>: Optional; if provided, used as the prefix of the summary tag name,
    which controls the tab name used for display on Tensorboard.


#### Returns:

A scalar `Tensor` of type `string`. Which contains a `Summary` protobuf.


#### Raises:

* <b>`ValueError`</b>: If tensor has the wrong shape or type.