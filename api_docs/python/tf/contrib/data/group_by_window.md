<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.group_by_window" />
</div>

# tf.contrib.data.group_by_window

``` python
group_by_window(
    key_func,
    reduce_func,
    window_size=None,
    window_size_func=None
)
```



Defined in [`tensorflow/contrib/data/python/ops/grouping.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/grouping.py).

A transformation that groups windows of elements by key and reduces them.

This transformation maps each consecutive element in a dataset to a key
using `key_func` and groups the elements by key. It then applies
`reduce_func` to at most `window_size_func(key)` elements matching the same
key. All execpt the final window for each key will contain
`window_size_func(key)` elements; the final window may be smaller.

You may provide either a constant `window_size` or a window size determined by
the key through `window_size_func`.

#### Args:

* <b>`key_func`</b>: A function mapping a nested structure of tensors
    (having shapes and types defined by `self.output_shapes` and
    `self.output_types`) to a scalar `tf.int64` tensor.
* <b>`reduce_func`</b>: A function mapping a key and a dataset of up to `batch_size`
    consecutive elements matching that key to another dataset.
* <b>`window_size`</b>: A `tf.int64` scalar `tf.Tensor`, representing the number of
    consecutive elements matching the same key to combine in a single
    batch, which will be passed to `reduce_func`. Mutually exclusive with
    `window_size_func`.
* <b>`window_size_func`</b>: A function mapping a key to a `tf.int64` scalar
    `tf.Tensor`, representing the number of consecutive elements matching
    the same key to combine in a single batch, which will be passed to
    `reduce_func`. Mutually exclusive with `window_size`.


#### Returns:

A `Dataset` transformation function, which can be passed to
[`tf.data.Dataset.apply`](../../../tf/data/Dataset.md#apply).


#### Raises:

* <b>`ValueError`</b>: if neither or both of {`window_size`, `window_size_func`} are
    passed.