<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.assert_rank_in" />
</div>

# tf.assert_rank_in

``` python
assert_rank_in(
    x,
    ranks,
    data=None,
    summarize=None,
    message=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/check_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/check_ops.py).

Assert `x` has rank in `ranks`.

Example of adding a dependency to an operation:

```python
with tf.control_dependencies([tf.assert_rank_in(x, (2, 4))]):
  output = tf.reduce_sum(x)
```

#### Args:

* <b>`x`</b>:  Numeric `Tensor`.
* <b>`ranks`</b>:  Iterable of scalar `Tensor` objects.
* <b>`data`</b>:  The tensors to print out if the condition is False.  Defaults to
    error message and first few entries of `x`.
* <b>`summarize`</b>: Print this many entries of each tensor.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional).
    Defaults to "assert_rank_in".


#### Returns:

Op raising `InvalidArgumentError` unless rank of `x` is in `ranks`.
If static checks determine `x` has matching rank, a `no_op` is returned.


#### Raises:

* <b>`ValueError`</b>:  If static checks determine `x` has mismatched rank.