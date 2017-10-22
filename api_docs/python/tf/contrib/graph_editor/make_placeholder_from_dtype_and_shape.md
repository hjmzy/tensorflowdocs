<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.make_placeholder_from_dtype_and_shape" />
</div>

# tf.contrib.graph_editor.make_placeholder_from_dtype_and_shape

### Aliases:

* `tf.contrib.graph_editor.make_placeholder_from_dtype_and_shape`
* `tf.contrib.graph_editor.ph`

``` python
make_placeholder_from_dtype_and_shape(
    dtype,
    shape=None,
    scope=None
)
```



Defined in [`tensorflow/contrib/graph_editor/util.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/util.py).

See the guides: [Graph Editor (contrib) > Module: util](../../../../../api_guides/python/contrib.graph_editor.md#Module_util), [Graph Editor (contrib) > Useful aliases](../../../../../api_guides/python/contrib.graph_editor.md#Useful_aliases)

Create a tf.placeholder for the Graph Editor.

Note that the correct graph scope must be set by the calling function.
The placeholder is named using the function placeholder_name (with no
tensor argument).

#### Args:

* <b>`dtype`</b>: the tensor type.
* <b>`shape`</b>: the tensor shape (optional).
* <b>`scope`</b>: absolute scope within which to create the placeholder. None
    means that the scope of t is preserved. "" means the root scope.

#### Returns:

A newly created tf.placeholder.