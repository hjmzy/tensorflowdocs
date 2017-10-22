<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.make_placeholder_from_tensor" />
</div>

# tf.contrib.graph_editor.make_placeholder_from_tensor

``` python
make_placeholder_from_tensor(
    t,
    scope=None
)
```



Defined in [`tensorflow/contrib/graph_editor/util.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/util.py).

See the guide: [Graph Editor (contrib) > Module: util](../../../../../api_guides/python/contrib.graph_editor.md#Module_util)

Create a `tf.placeholder` for the Graph Editor.

Note that the correct graph scope must be set by the calling function.

#### Args:

* <b>`t`</b>: a `tf.Tensor` whose name will be used to create the placeholder
    (see function placeholder_name).
* <b>`scope`</b>: absolute scope within which to create the placeholder. None
    means that the scope of `t` is preserved. `""` means the root scope.

#### Returns:

A newly created `tf.placeholder`.

#### Raises:

* <b>`TypeError`</b>: if `t` is not `None` or a `tf.Tensor`.