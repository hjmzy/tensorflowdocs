<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.random_uniform" />
</div>

# tf.keras.backend.random_uniform

``` python
random_uniform(
    shape,
    minval=0.0,
    maxval=1.0,
    dtype=None,
    seed=None
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Returns a tensor with uniform distribution of values.

#### Arguments:

* <b>`shape`</b>: A tuple of integers, the shape of tensor to create.
* <b>`minval`</b>: A float, lower boundary of the uniform distribution
        to draw samples.
* <b>`maxval`</b>: A float, upper boundary of the uniform distribution
        to draw samples.
* <b>`dtype`</b>: String, dtype of returned tensor.
* <b>`seed`</b>: Integer, random seed.


#### Returns:

A tensor.