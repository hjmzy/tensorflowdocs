<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.trainable_variables" />
</div>

# tf.trainable_variables

``` python
trainable_variables(scope=None)
```



Defined in [`tensorflow/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/python/ops/variables.py).

See the guide: [Variables > Variable helper functions](../../../api_guides/python/state_ops.md#Variable_helper_functions)

Returns all variables created with `trainable=True`.

When passed `trainable=True`, the `Variable()` constructor automatically
adds new variables to the graph collection
`GraphKeys.TRAINABLE_VARIABLES`. This convenience function returns the
contents of that collection.

#### Args:

* <b>`scope`</b>: (Optional.) A string. If supplied, the resulting list is filtered
    to include only items whose `name` attribute matches `scope` using
    `re.match`. Items without a `name` attribute are never returned if a
    scope is supplied. The choice of `re.match` means that a `scope` without
    special tokens filters by prefix.


#### Returns:

A list of Variable objects.