<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.assert_proper_iterable" />
</div>

# tf.assert_proper_iterable

``` python
assert_proper_iterable(values)
```



Defined in [`tensorflow/python/ops/check_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/check_ops.py).

See the guide: [Asserts and boolean checks](../../../api_guides/python/check_ops.md)

Static assert that values is a "proper" iterable.

`Ops` that expect iterables of `Tensor` can call this to validate input.
Useful since `Tensor`, `ndarray`, byte/text type are all iterables themselves.

#### Args:

* <b>`values`</b>:  Object to be checked.


#### Raises:

* <b>`TypeError`</b>:  If `values` is not iterable or is one of
    `Tensor`, `SparseTensor`, `np.array`, `tf.compat.bytes_or_text_types`.