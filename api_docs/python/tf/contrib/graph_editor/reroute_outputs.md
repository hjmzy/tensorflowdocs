<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.reroute_outputs" />
</div>

# tf.contrib.graph_editor.reroute_outputs

``` python
reroute_outputs(
    sgv0,
    sgv1
)
```



Defined in [`tensorflow/contrib/graph_editor/reroute.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/reroute.py).

See the guide: [Graph Editor (contrib) > Module: reroute](../../../../../api_guides/python/contrib.graph_editor.md#Module_reroute)

Re-route all the outputs of two operations.

#### Args:

* <b>`sgv0`</b>: the first subgraph to have its outputs swapped. This argument is
    converted to a subgraph using the same rules than the function
    subgraph.make_view.
* <b>`sgv1`</b>: the second subgraph to have its outputs swapped. This argument is
    converted to a subgraph using the same rules than the function
    subgraph.make_view.

#### Returns:

A tuple `(sgv0, sgv1)` of subgraph views with their outputs swapped.
  Note that the function argument sgv0 and sgv1 are also modified in place.

#### Raises:

* <b>`StandardError`</b>: if sgv0 or sgv1 cannot be converted to a SubGraphView using
    the same rules than the function subgraph.make_view.