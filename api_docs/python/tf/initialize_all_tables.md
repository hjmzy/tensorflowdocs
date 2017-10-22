<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initialize_all_tables" />
</div>

# tf.initialize_all_tables

``` python
initialize_all_tables(name='init_all_tables')
```



Defined in [`tensorflow/python/ops/lookup_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/lookup_ops.py).

See the guide: [Variables > Sparse Variable Updates](../../../api_guides/python/state_ops.md#Sparse_Variable_Updates)

Returns an Op that initializes all tables of the default graph. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.tables_initializer` instead.

#### Args:

* <b>`name`</b>: Optional name for the initialization op.


#### Returns:

An Op that initializes all tables.  Note that if there are
not tables the returned Op is a NoOp.