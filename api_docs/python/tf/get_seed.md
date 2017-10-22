<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.get_seed" />
</div>

# tf.get_seed

``` python
get_seed(op_seed)
```



Defined in [`tensorflow/python/framework/random_seed.py`](https://www.tensorflow.org/code/tensorflow/python/framework/random_seed.py).

See the guide: [Building Graphs > Defining new operations](../../../api_guides/python/framework.md#Defining_new_operations)

Returns the local seeds an operation should use given an op-specific seed.

Given operation-specific seed, `op_seed`, this helper function returns two
seeds derived from graph-level and op-level seeds. Many random operations
internally use the two seeds to allow user to change the seed globally for a
graph, or for only specific operations.

For details on how the graph-level seed interacts with op seeds, see
[`tf.set_random_seed`](../tf/set_random_seed.md).

#### Args:

* <b>`op_seed`</b>: integer.


#### Returns:

A tuple of two integers that should be used for the local seed of this
operation.