<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.get_single_element" />
</div>

# tf.contrib.data.get_single_element

``` python
get_single_element(dataset)
```



Defined in [`tensorflow/contrib/data/python/ops/dataset_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/dataset_ops.py).

Returns the single element in `dataset` as a nested structure of tensors.

This function enables you to use a [`tf.data.Dataset`](../../../tf/data/Dataset.md) in a stateless
"tensor-in tensor-out" expression, without creating a [`tf.data.Iterator`](../../../tf/data/Iterator.md).
This can be useful when your preprocessing transformations are expressed
as a `Dataset`, and you want to use the transformation at serving time.
For example:

```python
input_batch = tf.placeholder(tf.string, shape=[BATCH_SIZE])

def preprocessing_fn(input_str):
  # ...
  return image, label

dataset = (tf.data.Dataset.from_tensor_slices(input_batch)
           .map(preprocessing_fn, num_parallel_calls=BATCH_SIZE)
           .batch(BATCH_SIZE))

image_batch, label_batch = tf.contrib.data.get_single_element(dataset)
```

#### Args:

* <b>`dataset`</b>: A [`tf.data.Dataset`](../../../tf/data/Dataset.md) object containing a single element.


#### Returns:

A nested structure of [`tf.Tensor`](../../../tf/Tensor.md) objects, corresponding to the single
element of `dataset`.


#### Raises:

* <b>`TypeError`</b>: if `dataset` is not a `tf.data.Dataset` object.
  InvalidArgumentError (at runtime): if `dataset` does not contain exactly
    one element.