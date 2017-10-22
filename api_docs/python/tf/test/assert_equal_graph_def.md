<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.test.assert_equal_graph_def" />
</div>

# tf.test.assert_equal_graph_def

``` python
assert_equal_graph_def(
    actual,
    expected,
    checkpoint_v2=False
)
```



Defined in [`tensorflow/python/framework/test_util.py`](https://www.tensorflow.org/code/tensorflow/python/framework/test_util.py).

See the guide: [Testing > Utilities](../../../../api_guides/python/test.md#Utilities)

Asserts that two `GraphDef`s are (mostly) the same.

Compares two `GraphDef` protos for equality, ignoring versions and ordering of
nodes, attrs, and control inputs.  Node names are used to match up nodes
between the graphs, so the naming of nodes must be consistent.

#### Args:

* <b>`actual`</b>: The `GraphDef` we have.
* <b>`expected`</b>: The `GraphDef` we expected.
* <b>`checkpoint_v2`</b>: boolean determining whether to ignore randomized attribute
      values that appear in V2 checkpoints.


#### Raises:

* <b>`AssertionError`</b>: If the `GraphDef`s do not match.
* <b>`TypeError`</b>: If either argument is not a `GraphDef`.