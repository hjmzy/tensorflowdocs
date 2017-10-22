<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.enumerate_dataset" />
</div>

# tf.contrib.data.enumerate_dataset

``` python
enumerate_dataset(start=0)
```



Defined in [`tensorflow/contrib/data/python/ops/enumerate_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/enumerate_ops.py).

A transformation that enumerate the elements of a dataset.

It is Similar to python's `enumerate`.
For example:

```python
# NOTE: The following examples use `{ ... }` to represent the
# contents of a dataset.
a = { 1, 2, 3 }
b = { (7, 8), (9, 10) }

# The nested structure of the `datasets` argument determines the
# structure of elements in the resulting dataset.
a.apply(tf.contrib.data.enumerate(start=5)) == { (5, 1), (6, 2), (7, 3) }
b.apply(tf.contrib.data.enumerate()) == { (0, (7, 8)), (1, (9, 10)) }
```

#### Args:

* <b>`start`</b>: A `tf.int64` scalar `tf.Tensor`, representing the start
    value for enumeration.


#### Returns:

A `Dataset` transformation function, which can be passed to
[`tf.data.Dataset.apply`](../../../tf/data/Dataset.md#apply).