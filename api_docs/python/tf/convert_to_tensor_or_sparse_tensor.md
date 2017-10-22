<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.convert_to_tensor_or_sparse_tensor" />
</div>

# tf.convert_to_tensor_or_sparse_tensor

### Aliases:

* `tf.contrib.framework.convert_to_tensor_or_sparse_tensor`
* `tf.convert_to_tensor_or_sparse_tensor`

``` python
convert_to_tensor_or_sparse_tensor(
    value,
    dtype=None,
    name=None
)
```



Defined in [`tensorflow/python/framework/sparse_tensor.py`](https://www.tensorflow.org/code/tensorflow/python/framework/sparse_tensor.py).

See the guides: [Building Graphs > Utility functions](../../../api_guides/python/framework.md#Utility_functions), [Framework (contrib)](../../../api_guides/python/contrib.framework.md)

Converts value to a `SparseTensor` or `Tensor`.

#### Args:

* <b>`value`</b>: A `SparseTensor`, `SparseTensorValue`, or an object whose type has a
    registered `Tensor` conversion function.
* <b>`dtype`</b>: Optional element type for the returned tensor. If missing, the
    type is inferred from the type of `value`.
* <b>`name`</b>: Optional name to use if a new `Tensor` is created.


#### Returns:

A `SparseTensor` or `Tensor` based on `value`.


#### Raises:

* <b>`RuntimeError`</b>: If result type is incompatible with `dtype`.