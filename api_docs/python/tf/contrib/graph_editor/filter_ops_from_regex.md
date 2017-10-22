<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.filter_ops_from_regex" />
</div>

# tf.contrib.graph_editor.filter_ops_from_regex

``` python
filter_ops_from_regex(
    ops,
    regex
)
```



Defined in [`tensorflow/contrib/graph_editor/select.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/select.py).

See the guide: [Graph Editor (contrib) > Module: select](../../../../../api_guides/python/contrib.graph_editor.md#Module_select)

Get all the operations that match the given regex.

#### Args:

* <b>`ops`</b>: an object convertible to a list of `tf.Operation`.
* <b>`regex`</b>: a regular expression matching the operation's name.
    For example, `"^foo(/.*)?$"` will match all the operations in the "foo"
    scope.

#### Returns:

A list of `tf.Operation`.

#### Raises:

* <b>`TypeError`</b>: if ops cannot be converted to a list of `tf.Operation`.