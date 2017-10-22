<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.summarize_activation" />
</div>

# tf.contrib.layers.summarize_activation

``` python
summarize_activation(op)
```



Defined in [`tensorflow/contrib/layers/python/layers/summaries.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/summaries.py).

See the guide: [Layers (contrib) > Summaries](../../../../../api_guides/python/contrib.layers.md#Summaries)

Summarize an activation.

This applies the given activation and adds useful summaries specific to the
activation.

#### Args:

* <b>`op`</b>: The tensor to summarize (assumed to be a layer activation).

#### Returns:

The summary op created to summarize `op`.