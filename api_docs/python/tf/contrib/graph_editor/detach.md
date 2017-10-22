<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.detach" />
</div>

# tf.contrib.graph_editor.detach

``` python
detach(
    sgv,
    control_inputs=False,
    control_outputs=None,
    control_ios=None
)
```



Defined in [`tensorflow/contrib/graph_editor/edit.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/edit.py).

See the guide: [Graph Editor (contrib) > Module: edit](../../../../../api_guides/python/contrib.graph_editor.md#Module_edit)

Detach both the inputs and the outputs of a subgraph view.

#### Args:

* <b>`sgv`</b>: the subgraph view to be detached. This argument is converted to a
    subgraph using the same rules as the function subgraph.make_view.
    Note that sgv is modified in place.
* <b>`control_inputs`</b>: A boolean indicating whether control inputs are enabled.
* <b>`control_outputs`</b>: An instance of util.ControlOutputs or None. If not None,
    control outputs are enabled.
* <b>`control_ios`</b>:  An instance of util.ControlOutputs or None. If not None, both
    control inputs and control outputs are enabled. This is equivalent to set
    control_inputs to True and control_outputs to the util.ControlOutputs
    instance.

#### Returns:

A tuple `(sgv, detached_inputs, detached_outputs)` where:
`sgv` is a new subgraph view of the detached subgraph;
`detach_inputs` is a list of the created input placeholders;
`detach_outputs` is a list of the created output placeholders.

#### Raises:

* <b>`StandardError`</b>: if sgv cannot be converted to a SubGraphView using
    the same rules than the function subgraph.make_view.