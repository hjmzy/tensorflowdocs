<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.filter_ts_from_regex" />
</div>

# tf.contrib.graph_editor.filter_ts_from_regex

``` python
filter_ts_from_regex(
    ops,
    regex
)
```



Defined in [`tensorflow/contrib/graph_editor/select.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/select.py).

See the guide: [Graph Editor (contrib) > Module: select](../../../../../api_guides/python/contrib.graph_editor.md#Module_select)

Get all the tensors linked to ops that match the given regex.

#### Args:

* <b>`ops`</b>: an object convertible to a list of tf.Operation.
* <b>`regex`</b>: a regular expression matching the tensors' name.
    For example, "^foo(/.*)?:\d+$" will match all the tensors in the "foo"
    scope.

#### Returns:

A list of tf.Tensor.

#### Raises:

* <b>`TypeError`</b>: if ops cannot be converted to a list of tf.Operation.