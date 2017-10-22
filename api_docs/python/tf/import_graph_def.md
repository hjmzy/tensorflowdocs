<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.import_graph_def" />
</div>

# tf.import_graph_def

``` python
import_graph_def(
    graph_def,
    input_map=None,
    return_elements=None,
    name=None,
    op_dict=None,
    producer_op_list=None
)
```



Defined in [`tensorflow/python/framework/importer.py`](https://www.tensorflow.org/code/tensorflow/python/framework/importer.py).

See the guide: [Building Graphs > Utility functions](../../../api_guides/python/framework.md#Utility_functions)

Imports the graph from `graph_def` into the current default `Graph`. (deprecated arguments)

SOME ARGUMENTS ARE DEPRECATED. They will be removed in a future version.
Instructions for updating:
Please file an issue at https://github.com/tensorflow/tensorflow/issues if you depend on this feature.

This function provides a way to import a serialized TensorFlow
[`GraphDef`](https://www.tensorflow.org/code/tensorflow/core/framework/graph.proto)
protocol buffer, and extract individual objects in the `GraphDef` as
[`tf.Tensor`](../tf/Tensor.md) and [`tf.Operation`](../tf/Operation.md) objects. Once extracted,
these objects are placed into the current default `Graph`. See
[`tf.Graph.as_graph_def`](../tf/Graph.md#as_graph_def) for a way to create a `GraphDef`
proto.

#### Args:

* <b>`graph_def`</b>: A `GraphDef` proto containing operations to be imported into
    the default graph.
* <b>`input_map`</b>: A dictionary mapping input names (as strings) in `graph_def`
    to `Tensor` objects. The values of the named input tensors in the
    imported graph will be re-mapped to the respective `Tensor` values.
* <b>`return_elements`</b>: A list of strings containing operation names in
    `graph_def` that will be returned as `Operation` objects; and/or
    tensor names in `graph_def` that will be returned as `Tensor` objects.
* <b>`name`</b>: (Optional.) A prefix that will be prepended to the names in
    `graph_def`. Note that this does not apply to imported function names.
    Defaults to `"import"`.
* <b>`op_dict`</b>: (Optional.) Deprecated, do not use.
* <b>`producer_op_list`</b>: (Optional.) An `OpList` proto with the (possibly stripped)
    list of `OpDef`s used by the producer of the graph. If provided,
    unrecognized attrs for ops in `graph_def` that have their default value
    according to `producer_op_list` will be removed. This will allow some more
    `GraphDef`s produced by later binaries to be accepted by earlier binaries.


#### Returns:

A list of `Operation` and/or `Tensor` objects from the imported graph,
corresponding to the names in `return_elements`.


#### Raises:

* <b>`TypeError`</b>: If `graph_def` is not a `GraphDef` proto,
    `input_map` is not a dictionary mapping strings to `Tensor` objects,
    or `return_elements` is not a list of strings.
* <b>`ValueError`</b>: If `input_map`, or `return_elements` contains names that
    do not appear in `graph_def`, or `graph_def` is not well-formed (e.g.
    it refers to an unknown tensor).