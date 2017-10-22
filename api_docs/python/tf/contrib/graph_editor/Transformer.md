<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.Transformer" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.contrib.graph_editor.Transformer

## Class `Transformer`





Defined in [`tensorflow/contrib/graph_editor/transform.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/transform.py).

See the guide: [Graph Editor (contrib) > Module: transform](../../../../../api_guides/python/contrib.graph_editor.md#Module_transform)

Transform a subgraph into another one.

By default, the constructor create a transform which copy a subgraph and
replaces inputs with placeholders. This behavior can be modified by changing
the handlers.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__()
```

Transformer constructor.

The following members can be modified:
transform_op_handler: handle the transformation of a `tf.Operation`.
  This handler defaults to a simple copy.
assign_collections_handler: handle the assignment of collections.
  This handler defaults to assigning new collections created under the
  given name-scope.
transform_external_input_handler: handle the transform of the inputs to
  the given subgraph. This handler defaults to creating placeholders
  instead of the ops just before the input tensors of the subgraph.
transform_external_hidden_input_handler: handle the transform of the
  hidden inputs of the subgraph, that is, the inputs which are not listed
  in sgv.inputs. This handler defaults to a transform which keep the same
  input if the source and destination graphs are the same, otherwise
  use placeholders.
transform_original_op_handler: handle the transform of original_op. This
  handler defaults to transforming original_op only if they are in the
  subgraph, otherwise they are ignored.

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    sgv,
    dst_graph,
    dst_scope,
    src_scope='',
    reuse_dst_scope=False
)
```

Execute the transformation.

#### Args:

* <b>`sgv`</b>: the source subgraph-view.
* <b>`dst_graph`</b>: the destination graph.
* <b>`dst_scope`</b>: the destination scope.
* <b>`src_scope`</b>: the source scope, which specify the path from which the
    relative path of the transformed nodes are computed. For instance, if
    src_scope is a/ and dst_scoped is b/, then the node a/x/y will have a
    relative path of x/y and will be transformed into b/x/y.
* <b>`reuse_dst_scope`</b>: if True the dst_scope is re-used if it already exists.
    Otherwise, the scope is given a unique name based on the one given
    by appending an underscore followed by a digit (default).

#### Returns:

A tuple `(sgv, info)` where:
  `sgv` is the transformed subgraph view;
  `info` is an instance of TransformerInfo containing
  information about the transform, including mapping between
  original and transformed tensors and operations.

#### Raises:

* <b>`ValueError`</b>: if the arguments are invalid.



