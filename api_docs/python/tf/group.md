<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.group" />
</div>

# tf.group

``` python
group(
    *inputs,
    **kwargs
)
```



Defined in [`tensorflow/python/ops/control_flow_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/control_flow_ops.py).

See the guide: [Control Flow > Control Flow Operations](../../../api_guides/python/control_flow_ops.md#Control_Flow_Operations)

Create an op that groups multiple operations.

When this op finishes, all ops in `input` have finished. This op has no
output.

See also [tuple](../tf/tuple.md) and
[control_dependencies](../tf/control_dependencies.md).

#### Args:

* <b>`*inputs`</b>: Zero or more tensors to group.
* <b>`**kwargs`</b>: Optional parameters to pass when constructing the NodeDef.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

An Operation that executes all its inputs.


#### Raises:

* <b>`ValueError`</b>: If an unknown keyword argument is provided.