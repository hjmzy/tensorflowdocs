<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.assign_from_values" />
</div>

# tf.contrib.framework.assign_from_values

``` python
assign_from_values(var_names_to_values)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/variables.py).

See the guide: [Framework (contrib) > Variables](../../../../../api_guides/python/contrib.framework.md#Variables)

Creates an assignment operation from a given mapping.

This function provides a mechanism for performing assignment of variables
to values in a way that does not fill the graph with large assignment values.

#### Args:

* <b>`var_names_to_values`</b>: A map from variable names to values.


#### Returns:

* <b>`assign_op`</b>: An `Operation` that assigns each of the given variables to the
    requested values.
* <b>`feed_dict`</b>: The feed dictionary to use when evaluating `assign_op`.


#### Raises:

* <b>`ValueError`</b>: if any of the given variable names were not found.