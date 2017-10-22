<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.copy_op_handler" />
</div>

# tf.contrib.graph_editor.copy_op_handler

``` python
copy_op_handler(
    info,
    op,
    copy_shape=True
)
```



Defined in [`tensorflow/contrib/graph_editor/transform.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/transform.py).

See the guide: [Graph Editor (contrib) > Module: transform](../../../../../api_guides/python/contrib.graph_editor.md#Module_transform)

Copy a `tf.Operation`.

#### Args:

* <b>`info`</b>: Transform._TmpInfo instance.
* <b>`op`</b>: the `tf.Operation` to be copied.
* <b>`copy_shape`</b>: also copy the shape of the tensor

#### Returns:

A `(op, op_outputs)` tuple containing the transformed op and its outputs.