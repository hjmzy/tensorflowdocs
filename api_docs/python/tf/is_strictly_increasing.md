<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.is_strictly_increasing" />
</div>

# tf.is_strictly_increasing

``` python
is_strictly_increasing(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/check_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/check_ops.py).

See the guides: [Asserts and boolean checks](../../../api_guides/python/check_ops.md), [Framework (contrib)](../../../api_guides/python/contrib.framework.md)

Returns `True` if `x` is strictly increasing.

Elements of `x` are compared in row-major order.  The tensor `[x[0],...]`
is strictly increasing if for every adjacent pair we have `x[i] < x[i+1]`.
If `x` has less than two elements, it is trivially strictly increasing.

See also:  `is_non_decreasing`

#### Args:

* <b>`x`</b>: Numeric `Tensor`.
* <b>`name`</b>: A name for this operation (optional).
    Defaults to "is_strictly_increasing"


#### Returns:

Boolean `Tensor`, equal to `True` iff `x` is strictly increasing.


#### Raises:

* <b>`TypeError`</b>: if `x` is not a numeric tensor.