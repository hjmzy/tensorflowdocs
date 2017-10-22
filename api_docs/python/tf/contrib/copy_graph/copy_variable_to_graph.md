<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.copy_graph.copy_variable_to_graph" />
</div>

# tf.contrib.copy_graph.copy_variable_to_graph

``` python
copy_variable_to_graph(
    org_instance,
    to_graph,
    scope=''
)
```



Defined in [`tensorflow/contrib/copy_graph/python/util/copy_elements.py`](https://www.tensorflow.org/code/tensorflow/contrib/copy_graph/python/util/copy_elements.py).

Given a `Variable` instance from one `Graph`, initializes and returns
a copy of it from another `Graph`, under the specified scope
(default `""`).

#### Args:

* <b>`org_instance`</b>: A `Variable` from some `Graph`.
* <b>`to_graph`</b>: The `Graph` to copy the `Variable` to.
* <b>`scope`</b>: A scope for the new `Variable` (default `""`).


#### Returns:

The copied `Variable` from `to_graph`.


#### Raises:

* <b>`TypeError`</b>: If `org_instance` is not a `Variable`.