<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.name_scope" />
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.name_scope

## Class `name_scope`



### Aliases:

* Class `tf.keras.backend.name_scope`
* Class `tf.name_scope`



Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

See the guide: [Building Graphs > Utility functions](../../../api_guides/python/framework.md#Utility_functions)

A context manager for use when defining a Python op.

This context manager validates that the given `values` are from the
same graph, makes that graph the default graph, and pushes a
name scope in that graph (see
[`tf.Graph.name_scope`](../tf/Graph.md#name_scope)
for more details on that).

For example, to define a new Python op called `my_op`:

```python
def my_op(a, b, c, name=None):
  with tf.name_scope(name, "MyOp", [a, b, c]) as scope:
    a = tf.convert_to_tensor(a, name="a")
    b = tf.convert_to_tensor(b, name="b")
    c = tf.convert_to_tensor(c, name="c")
    # Define some computation that uses `a`, `b`, and `c`.
    return foo_op(..., name=scope)
```

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    name,
    default_name=None,
    values=None
)
```

Initialize the context manager.

#### Args:

* <b>`name`</b>: The name argument that is passed to the op function.
* <b>`default_name`</b>: The default name to use if the `name` argument is `None`.
* <b>`values`</b>: The list of `Tensor` arguments that are passed to the op function.

<h3 id="__enter__"><code>__enter__</code></h3>

``` python
__enter__()
```

Start the scope block.

#### Returns:

The scope name.


#### Raises:

* <b>`ValueError`</b>: if neither `name` nor `default_name` is provided
    but `values` are.

<h3 id="__exit__"><code>__exit__</code></h3>

``` python
__exit__(
    type_arg,
    value_arg,
    traceback_arg
)
```





