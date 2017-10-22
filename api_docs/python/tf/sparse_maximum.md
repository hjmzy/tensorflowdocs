<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sparse_maximum" />
</div>

# tf.sparse_maximum

``` python
sparse_maximum(
    sp_a,
    sp_b,
    name=None
)
```



Defined in [`tensorflow/python/ops/sparse_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/sparse_ops.py).

See the guide: [Sparse Tensors > Math Operations](../../../api_guides/python/sparse_ops.md#Math_Operations)

Returns the element-wise max of two SparseTensors.

Assumes the two SparseTensors have the same shape, i.e., no broadcasting.
Example:

```python
sp_zero = sparse_tensor.SparseTensor([[0]], [0], [7])
sp_one = sparse_tensor.SparseTensor([[1]], [1], [7])
res = tf.sparse_maximum(sp_zero, sp_one).eval()
# "res" should be equal to SparseTensor([[0], [1]], [0, 1], [7]).
```

#### Args:

* <b>`sp_a`</b>: a `SparseTensor` operand whose dtype is real, and indices
    lexicographically ordered.
* <b>`sp_b`</b>: the other `SparseTensor` operand with the same requirements (and the
    same shape).
* <b>`name`</b>: optional name of the operation.

#### Returns:

* <b>`output`</b>: the output SparseTensor.