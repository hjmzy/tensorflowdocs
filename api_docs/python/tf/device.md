<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.device" />
</div>

# tf.device

``` python
device(device_name_or_function)
```



Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

See the guide: [Building Graphs > Utility functions](../../../api_guides/python/framework.md#Utility_functions)

Wrapper for `Graph.device()` using the default graph.

See
[`tf.Graph.device`](../tf/Graph.md#device)
for more details.

#### Args:

* <b>`device_name_or_function`</b>: The device name or function to use in
    the context.


#### Returns:

A context manager that specifies the default device to use for newly
created ops.