<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.get_tensors" />
</div>

# tf.contrib.graph_editor.get_tensors

``` python
get_tensors(graph)
```



Defined in [`tensorflow/contrib/graph_editor/util.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/util.py).

See the guide: [Graph Editor (contrib) > Module: util](../../../../../api_guides/python/contrib.graph_editor.md#Module_util)

get all the tensors which are input or output of an op in the graph.

#### Args:

* <b>`graph`</b>: a `tf.Graph`.

#### Returns:

A list of `tf.Tensor`.

#### Raises:

* <b>`TypeError`</b>: if graph is not a `tf.Graph`.