<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.layers.flatten" />
</div>

# tf.layers.flatten

``` python
flatten(
    inputs,
    name=None
)
```



Defined in [`tensorflow/python/layers/core.py`](https://www.tensorflow.org/code/tensorflow/python/layers/core.py).

Flattens an input tensor while preserving the batch axis (axis 0).

#### Arguments:

* <b>`inputs`</b>: Tensor input.
* <b>`name`</b>: The name of the layer (string).


#### Returns:

  Reshaped tensor.

Examples:

```
  x = tf.placeholder(shape=(None, 4, 4), dtype='float32')
  y = flatten(x)
  # now `y` has shape `(None, 16)`

  x = tf.placeholder(shape=(None, 3, None), dtype='float32')
  y = flatten(x)
  # now `y` has shape `(None, None)`
```