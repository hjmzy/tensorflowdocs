<!-- DO NOT EDIT! Automatically generated file. -->
# Sparse Tensors

Note: Functions taking `Tensor` arguments can also take anything accepted by
[`tf.convert_to_tensor`](../../api_docs/python/tf/convert_to_tensor.md).

[TOC]

<h2 id="Sparse_Tensor_Representation">Sparse Tensor Representation</h2>

TensorFlow supports a `SparseTensor` representation for data that is sparse
in multiple dimensions. Contrast this representation with `IndexedSlices`,
which is efficient for representing tensors that are sparse in their first
dimension, and dense along all other dimensions.

*   [`tf.SparseTensor`](../../api_docs/python/tf/SparseTensor.md)
*   [`tf.SparseTensorValue`](../../api_docs/python/tf/SparseTensorValue.md)

<h2 id="Conversion">Conversion</h2>

*   [`tf.sparse_to_dense`](../../api_docs/python/tf/sparse_to_dense.md)
*   [`tf.sparse_tensor_to_dense`](../../api_docs/python/tf/sparse_tensor_to_dense.md)
*   [`tf.sparse_to_indicator`](../../api_docs/python/tf/sparse_to_indicator.md)
*   [`tf.sparse_merge`](../../api_docs/python/tf/sparse_merge.md)

<h2 id="Manipulation">Manipulation</h2>

*   [`tf.sparse_concat`](../../api_docs/python/tf/sparse_concat.md)
*   [`tf.sparse_reorder`](../../api_docs/python/tf/sparse_reorder.md)
*   [`tf.sparse_reshape`](../../api_docs/python/tf/sparse_reshape.md)
*   [`tf.sparse_split`](../../api_docs/python/tf/sparse_split.md)
*   [`tf.sparse_retain`](../../api_docs/python/tf/sparse_retain.md)
*   [`tf.sparse_reset_shape`](../../api_docs/python/tf/sparse_reset_shape.md)
*   [`tf.sparse_fill_empty_rows`](../../api_docs/python/tf/sparse_fill_empty_rows.md)
*   [`tf.sparse_transpose`](../../api_docs/python/tf/sparse_transpose.md)

<h2 id="Reduction">Reduction</h2>
*   [`tf.sparse_reduce_sum`](../../api_docs/python/tf/sparse_reduce_sum.md)
*   [`tf.sparse_reduce_sum_sparse`](../../api_docs/python/tf/sparse_reduce_sum_sparse.md)

<h2 id="Math_Operations">Math Operations</h2>
*   [`tf.sparse_add`](../../api_docs/python/tf/sparse_add.md)
*   [`tf.sparse_softmax`](../../api_docs/python/tf/sparse_softmax.md)
*   [`tf.sparse_tensor_dense_matmul`](../../api_docs/python/tf/sparse_tensor_dense_matmul.md)
*   [`tf.sparse_maximum`](../../api_docs/python/tf/sparse_maximum.md)
*   [`tf.sparse_minimum`](../../api_docs/python/tf/sparse_minimum.md)
