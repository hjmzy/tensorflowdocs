<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.get_or_create_global_step" />
</div>

# tf.contrib.framework.get_or_create_global_step

``` python
get_or_create_global_step(graph=None)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/variables.py).

See the guide: [Framework (contrib) > Variables](../../../../../api_guides/python/contrib.framework.md#Variables)

Returns and create (if necessary) the global step tensor. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Please switch to tf.train.get_or_create_global_step

#### Args:

* <b>`graph`</b>: The graph in which to create the global step tensor. If missing, use
    default graph.


#### Returns:

The global step tensor.