<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.summarize_tensor" />
</div>

# tf.contrib.layers.summarize_tensor

``` python
summarize_tensor(
    tensor,
    tag=None
)
```



Defined in [`tensorflow/contrib/layers/python/layers/summaries.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/summaries.py).

See the guide: [Layers (contrib) > Summaries](../../../../../api_guides/python/contrib.layers.md#Summaries)

Summarize a tensor using a suitable summary type.

This function adds a summary op for `tensor`. The type of summary depends on
the shape of `tensor`. For scalars, a `scalar_summary` is created, for all
other tensors, `histogram_summary` is used.

#### Args:

* <b>`tensor`</b>: The tensor to summarize
* <b>`tag`</b>: The tag to use, if None then use tensor's op's name.


#### Returns:

The summary op created or None for string tensors.