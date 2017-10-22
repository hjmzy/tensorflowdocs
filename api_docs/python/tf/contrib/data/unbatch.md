<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.unbatch" />
</div>

# tf.contrib.data.unbatch

``` python
unbatch()
```



Defined in [`tensorflow/contrib/data/python/ops/batching.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/batching.py).

A Transformation which splits the elements of a dataset.

For example, if elements of the dataset are shaped `[B, a0, a1, ...]`,
where `B` may vary from element to element, then for each element in
the dataset, the unbatched dataset will contain `B` consecutive elements
of shape `[a0, a1, ...]`.

#### Returns:

A `Dataset` transformation function, which can be passed to
[`tf.data.Dataset.apply`](../../../tf/data/Dataset.md#apply).