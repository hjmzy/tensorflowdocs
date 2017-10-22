<!-- DO NOT EDIT! Automatically generated file. -->
# Graph Editor (contrib)
[TOC]

TensorFlow Graph Editor.

The TensorFlow Graph Editor library allows for modification of an existing
`tf.Graph` instance in-place.

The author's github username is [purpledog](https://github.com/purpledog).

<h2 id="Library_overview">Library overview</h2>

Appending new nodes is the only graph editing operation allowed by the
TensorFlow core library. The Graph Editor library is an attempt to allow for
other kinds of editing operations, namely, *rerouting* and *transforming*.

* *rerouting* is a local operation consisting in re-plugging existing tensors
  (the edges of the graph). Operations (the nodes) are not modified by this
  operation. For example, rerouting can be used to insert an operation adding
  noise in place of an existing tensor.
* *transforming* is a global operation consisting in transforming a graph into
  another. By default, a transformation is a simple copy but it can be
  customized to achieved other goals. For instance, a graph can be transformed
  into another one in which noise is added after all the operations of a
  specific type.

**Important: modifying a graph in-place with the Graph Editor must be done
`offline`, that is, without any active sessions.**

Of course new operations can be appended online but Graph Editor specific
operations like rerouting and transforming can currently only be done offline.

Here is an example of what you **cannot** do:

* Build a graph.
* Create a session and run the graph.
* Modify the graph with the Graph Editor.
* Re-run the graph with the `same` previously created session.

To edit an already running graph, follow these steps:

* Build a graph.
* Create a session and run the graph.
* Save the graph state and terminate the session
* Modify the graph with the Graph Editor.
* create a new session and restore the graph state
* Re-run the graph with the newly created session.

Note that this procedure is very costly because a new session must be created
after any modifications. Among other things, it takes time because the entire
graph state must be saved and restored again.

<h2 id="Sub_graph">Sub-graph</h2>

Most of the functions in the Graph Editor library operate on *sub-graph*.
More precisely, they take as input arguments instances of the SubGraphView class
(or anything which can be converted to it). Doing so allows the same function
to transparently operate on single operations as well as sub-graph of any size.

A subgraph can be created in several ways:

* using a list of ops:

```python
my_sgv = ge.sgv(ops)
```

* from a name scope:

```python
my_sgv = ge.sgv_scope("foo/bar", graph=tf.get_default_graph())
```

* using regular expression:

```python
my_sgv = ge.sgv("foo/.*/.*read$", graph=tf.get_default_graph())
```

Note that the Graph Editor is meant to manipulate several graphs at the same
time, typically during transform or copy operation. For that reason,
to avoid any confusion, the default graph is never used and the graph on
which to operate must always be given explicitly. This is the reason why
*`graph=tf.get_default_graph()`* is used in the code snippets above.

<h2 id="Modules_overview">Modules overview</h2>

* util: utility functions.
* select: various selection methods of TensorFlow tensors and operations.
* match: TensorFlow graph matching. Think of this as regular expressions for
  graphs (but not quite yet).
* reroute: various ways of rerouting tensors to different consuming ops like
  *swap* or *reroute_a2b*.
* subgraph: the SubGraphView class, which enables subgraph manipulations in a
  TensorFlow `tf.Graph`.
* edit: various editing functions operating on subgraphs like *detach*,
  *connect* or *bypass*.
* transform: the Transformer class, which enables transforming
  (or simply copying) a subgraph into another one.

<h2 id="Module_util">Module: util</h2>

*   [`tf.contrib.graph_editor.make_list_of_op`](../../api_docs/python/tf/contrib/graph_editor/make_list_of_op.md)
*   [`tf.contrib.graph_editor.get_tensors`](../../api_docs/python/tf/contrib/graph_editor/get_tensors.md)
*   [`tf.contrib.graph_editor.make_list_of_t`](../../api_docs/python/tf/contrib/graph_editor/make_list_of_t.md)
*   [`tf.contrib.graph_editor.get_generating_ops`](../../api_docs/python/tf/contrib/graph_editor/get_generating_ops.md)
*   [`tf.contrib.graph_editor.get_consuming_ops`](../../api_docs/python/tf/contrib/graph_editor/get_consuming_ops.md)
*   [`tf.contrib.graph_editor.ControlOutputs`](../../api_docs/python/tf/contrib/graph_editor/ControlOutputs.md)
*   [`tf.contrib.graph_editor.placeholder_name`](../../api_docs/python/tf/contrib/graph_editor/placeholder_name.md)
*   [`tf.contrib.graph_editor.make_placeholder_from_tensor`](../../api_docs/python/tf/contrib/graph_editor/make_placeholder_from_tensor.md)
*   [`tf.contrib.graph_editor.make_placeholder_from_dtype_and_shape`](../../api_docs/python/tf/contrib/graph_editor/make_placeholder_from_dtype_and_shape.md)

<h2 id="Module_select">Module: select</h2>

*   [`tf.contrib.graph_editor.filter_ts`](../../api_docs/python/tf/contrib/graph_editor/filter_ts.md)
*   [`tf.contrib.graph_editor.filter_ts_from_regex`](../../api_docs/python/tf/contrib/graph_editor/filter_ts_from_regex.md)
*   [`tf.contrib.graph_editor.filter_ops`](../../api_docs/python/tf/contrib/graph_editor/filter_ops.md)
*   [`tf.contrib.graph_editor.filter_ops_from_regex`](../../api_docs/python/tf/contrib/graph_editor/filter_ops_from_regex.md)
*   [`tf.contrib.graph_editor.get_name_scope_ops`](../../api_docs/python/tf/contrib/graph_editor/get_name_scope_ops.md)
*   [`tf.contrib.graph_editor.check_cios`](../../api_docs/python/tf/contrib/graph_editor/check_cios.md)
*   [`tf.contrib.graph_editor.get_ops_ios`](../../api_docs/python/tf/contrib/graph_editor/get_ops_ios.md)
*   [`tf.contrib.graph_editor.compute_boundary_ts`](../../api_docs/python/tf/contrib/graph_editor/compute_boundary_ts.md)
*   [`tf.contrib.graph_editor.get_within_boundary_ops`](../../api_docs/python/tf/contrib/graph_editor/get_within_boundary_ops.md)
*   [`tf.contrib.graph_editor.get_forward_walk_ops`](../../api_docs/python/tf/contrib/graph_editor/get_forward_walk_ops.md)
*   [`tf.contrib.graph_editor.get_backward_walk_ops`](../../api_docs/python/tf/contrib/graph_editor/get_backward_walk_ops.md)
*   [`tf.contrib.graph_editor.get_walks_intersection_ops`](../../api_docs/python/tf/contrib/graph_editor/get_walks_intersection_ops.md)
*   [`tf.contrib.graph_editor.get_walks_union_ops`](../../api_docs/python/tf/contrib/graph_editor/get_walks_union_ops.md)
*   [`tf.contrib.graph_editor.select_ops`](../../api_docs/python/tf/contrib/graph_editor/select_ops.md)
*   [`tf.contrib.graph_editor.select_ts`](../../api_docs/python/tf/contrib/graph_editor/select_ts.md)
*   [`tf.contrib.graph_editor.select_ops_and_ts`](../../api_docs/python/tf/contrib/graph_editor/select_ops_and_ts.md)

<h2 id="Module_subgraph">Module: subgraph</h2>

*   [`tf.contrib.graph_editor.SubGraphView`](../../api_docs/python/tf/contrib/graph_editor/SubGraphView.md)
*   [`tf.contrib.graph_editor.make_view`](../../api_docs/python/tf/contrib/graph_editor/make_view.md)
*   [`tf.contrib.graph_editor.make_view_from_scope`](../../api_docs/python/tf/contrib/graph_editor/make_view_from_scope.md)

<h2 id="Module_reroute">Module: reroute</h2>

*   [`tf.contrib.graph_editor.swap_ts`](../../api_docs/python/tf/contrib/graph_editor/swap_ts.md)
*   [`tf.contrib.graph_editor.reroute_ts`](../../api_docs/python/tf/contrib/graph_editor/reroute_ts.md)
*   [`tf.contrib.graph_editor.swap_inputs`](../../api_docs/python/tf/contrib/graph_editor/swap_inputs.md)
*   [`tf.contrib.graph_editor.reroute_inputs`](../../api_docs/python/tf/contrib/graph_editor/reroute_inputs.md)
*   [`tf.contrib.graph_editor.swap_outputs`](../../api_docs/python/tf/contrib/graph_editor/swap_outputs.md)
*   [`tf.contrib.graph_editor.reroute_outputs`](../../api_docs/python/tf/contrib/graph_editor/reroute_outputs.md)
*   [`tf.contrib.graph_editor.swap_ios`](../../api_docs/python/tf/contrib/graph_editor/swap_ios.md)
*   [`tf.contrib.graph_editor.reroute_ios`](../../api_docs/python/tf/contrib/graph_editor/reroute_ios.md)
*   [`tf.contrib.graph_editor.remove_control_inputs`](../../api_docs/python/tf/contrib/graph_editor/remove_control_inputs.md)
*   [`tf.contrib.graph_editor.add_control_inputs`](../../api_docs/python/tf/contrib/graph_editor/add_control_inputs.md)

<h2 id="Module_edit">Module: edit</h2>

*   [`tf.contrib.graph_editor.detach_control_inputs`](../../api_docs/python/tf/contrib/graph_editor/detach_control_inputs.md)
*   [`tf.contrib.graph_editor.detach_control_outputs`](../../api_docs/python/tf/contrib/graph_editor/detach_control_outputs.md)
*   [`tf.contrib.graph_editor.detach_inputs`](../../api_docs/python/tf/contrib/graph_editor/detach_inputs.md)
*   [`tf.contrib.graph_editor.detach_outputs`](../../api_docs/python/tf/contrib/graph_editor/detach_outputs.md)
*   [`tf.contrib.graph_editor.detach`](../../api_docs/python/tf/contrib/graph_editor/detach.md)
*   [`tf.contrib.graph_editor.connect`](../../api_docs/python/tf/contrib/graph_editor/connect.md)
*   [`tf.contrib.graph_editor.bypass`](../../api_docs/python/tf/contrib/graph_editor/bypass.md)

<h2 id="Module_transform">Module: transform</h2>

*   [`tf.contrib.graph_editor.replace_t_with_placeholder_handler`](../../api_docs/python/tf/contrib/graph_editor/replace_t_with_placeholder_handler.md)
*   [`tf.contrib.graph_editor.keep_t_if_possible_handler`](../../api_docs/python/tf/contrib/graph_editor/keep_t_if_possible_handler.md)
*   [`tf.contrib.graph_editor.assign_renamed_collections_handler`](../../api_docs/python/tf/contrib/graph_editor/assign_renamed_collections_handler.md)
*   [`tf.contrib.graph_editor.transform_op_if_inside_handler`](../../api_docs/python/tf/contrib/graph_editor/transform_op_if_inside_handler.md)
*   [`tf.contrib.graph_editor.copy_op_handler`](../../api_docs/python/tf/contrib/graph_editor/copy_op_handler.md)
*   [`tf.contrib.graph_editor.Transformer`](../../api_docs/python/tf/contrib/graph_editor/Transformer.md)
*   [`tf.contrib.graph_editor.copy`](../../api_docs/python/tf/contrib/graph_editor/copy.md)
*   [`tf.contrib.graph_editor.copy_with_input_replacements`](../../api_docs/python/tf/contrib/graph_editor/copy_with_input_replacements.md)
*   [`tf.contrib.graph_editor.graph_replace`](../../api_docs/python/tf/contrib/graph_editor/graph_replace.md)

<h2 id="Useful_aliases">Useful aliases</h2>

*   [`tf.contrib.graph_editor.ph`](../../api_docs/python/tf/contrib/graph_editor/make_placeholder_from_dtype_and_shape.md)
*   [`tf.contrib.graph_editor.sgv`](../../api_docs/python/tf/contrib/graph_editor/make_view.md)
*   [`tf.contrib.graph_editor.sgv_scope`](../../api_docs/python/tf/contrib/graph_editor/make_view_from_scope.md)
