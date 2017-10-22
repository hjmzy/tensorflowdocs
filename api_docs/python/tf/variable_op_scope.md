<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.variable_op_scope" />
</div>

# tf.variable_op_scope

``` python
variable_op_scope(
    values,
    name_or_scope,
    default_name=None,
    initializer=None,
    regularizer=None,
    caching_device=None,
    partitioner=None,
    custom_getter=None,
    reuse=None,
    dtype=None,
    use_resource=None,
    constraint=None
)
```



Defined in [`tensorflow/python/ops/variable_scope.py`](https://www.tensorflow.org/code/tensorflow/python/ops/variable_scope.py).

See the guide: [Variables > Sharing Variables](../../../api_guides/python/state_ops.md#Sharing_Variables)

Deprecated: context manager for defining an op that creates variables.