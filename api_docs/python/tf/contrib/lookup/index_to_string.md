<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.lookup.index_to_string" />
</div>

# tf.contrib.lookup.index_to_string

``` python
index_to_string(
    tensor,
    mapping,
    default_value='UNK',
    name=None
)
```



Defined in [`tensorflow/contrib/lookup/lookup_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/lookup/lookup_ops.py).

Maps `tensor` of indices into string values based on `mapping`. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2017-01-07.
Instructions for updating:
This op will be removed after the deprecation date. Please switch to index_to_string_table_from_tensor and call the lookup method of the returned table.

This operation converts `int64` indices into string values. The mapping is
initialized from a string `mapping` tensor where each element is a value and
the corresponding index within the tensor is the key.

Any input which does not have a corresponding index in 'mapping'
(an out-of-vocabulary entry) is assigned the `default_value`

The underlying table must be initialized by calling
`tf.tables_initializer.run()` once.

For example:

```python
mapping_string = tf.constant(["emerson", "lake", "palmer"])
indices = tf.constant([1, 5], tf.int64)
values = tf.contrib.lookup.index_to_string(
    indices, mapping=mapping_string, default_value="UNKNOWN")
...
tf.tables_initializer().run()

values.eval() ==> ["lake", "UNKNOWN"]
```

#### Args:

* <b>`tensor`</b>: A `int64` `Tensor` with the indices to map to strings.
* <b>`mapping`</b>: A 1-D string `Tensor` that specifies the strings to map from
    indices.
* <b>`default_value`</b>: The string value to use for out-of-vocabulary indices.
* <b>`name`</b>: A name for this op (optional).


#### Returns:

The strings values associated to the indices. The resultant dense
feature value tensor has the same shape as the corresponding `indices`.